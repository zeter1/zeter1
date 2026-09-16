**Язык / Language:** [Русский](REVIEW_GUIDE.md) · **English**

# Technical portfolio review guide

This page shows **where** the most representative engineering decisions live in the repositories. It does not replace each project's README; the goal is to give a reviewer a short path from a claim to code, a test, or a verification step.

## 5-minute review

If time is limited, open these four projects and jump directly to the listed locations:

1. **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** — `screen_recorder/`, `verify_project.py`, `verify_capture_recovery.py`, `verify_save_safety.py`, `.github/workflows/validate.yml`.
2. **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** — `bsod_investigator.py`, built-in `--self-test`, `.github/workflows/ci.yml`, `docs/`.
3. **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** — `voiceflow.py`, `docs/`, `.github/workflows/python-check.yml`.
4. **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** — `app/`, `tools/check_project.py`, `problem_logs.py`, `.github/workflows/ci.yml`.

Together they show Windows desktop work, multimedia, system diagnostics, local AI, hybrid desktop/web architecture, and automated verification.

## Engineering evidence map

| What to evaluate | Project | Where to look | What it demonstrates |
|---|---|---|---|
| Long-running multimedia operation management | Screen Recorder Pro | `screen_recorder/`, `verify_capture_recovery.py`, `verify_save_safety.py` | external FFmpeg lifecycle, recovery, and output safety |
| Real regression / structural checks | Screen Recorder Pro | `verify_project.py`, `verify_recording_publication.py`, `.github/workflows/validate.yml` | automated checks for architectural and user-facing invariants |
| Evidence-based Windows diagnostics | BSOD Investigator | `bsod_investigator.py`, `docs/`, `--self-test` | dump/event/driver evidence processing and reproducible self-check logic |
| Local speech-to-text pipeline | VoiceFlow | `voiceflow.py`, `docs/` | faster-whisper, CPU/CUDA paths, Windows input, background work |
| Reliable video-download pipeline | Universal Video Downloader | `src/`, `tests/`, `problem_log_validator.py` | separation of downloader/format/diagnostics logic and offline regression tests |
| Long AI/multimedia pipeline | Video Translator Pro | `videotranslator/`, `tests/`, `tools/`, `AGENTS.md` | checkpoints, recovery, staged processing, and AI-friendly structure |
| Multi-source parsing | Vacancy Parser Pro | `job_scraper.py`, `problem_logging.py`, `tests/` | fault isolation, normalization/deduplication, and source diagnostics |
| Hybrid desktop/web architecture | ZeTer OS | `app/`, `tools/check_project.py`, `problem_logs.py` | Python/native bridge + JavaScript UI + project verification |
| Windows system-utility safety | Windows PC Locker | `computer_locker.pyw`, `--self-test`, `.github/workflows/windows-checks.yml` | WinAPI/WTS/power-management flow and safe self-test |
| Windows TTS / long-running jobs | Text to MP3 | `text_to_mp3.py`, `.github/workflows/python-check.yml` | SAPI/COM pipeline and Windows-specific application logic |

## 15-minute review

### 1. Architecture

Compare how projects of different ages separate responsibilities:

- `Screen-Recorder-Pro/screen_recorder/` — modular desktop application;
- `Universal-Video-Downloader/src/` — downloader with separate tests/scripts/docs;
- `Video-Translator-Pro/videotranslator/` — package structure for a long-running pipeline;
- `ZeTer-OS/app/` — hybrid frontend/backend;
- `Vacancy-Parser-Pro` — separate scraper / GUI / logging layers.

For `BSOD-Investigator`, `VoiceFlow`, and `Text-to-MP3-Windows`, the current size of the legacy entry module is also worth noting. They are real working applications where further decomposition remains an explicit engineering task rather than something hidden by marketing copy.

### 2. Reliability of long-running operations

Inspect:

- checkpoints and recovery in `Video-Translator-Pro`;
- FFmpeg management and capture recovery in `Screen-Recorder-Pro`;
- recovery of long TTS/MP3 jobs in `Text-to-MP3-Windows`;
- timeout/retry/fallback behavior in network-heavy parts of `Universal-Video-Downloader` and `Vacancy-Parser-Pro`.

### 3. Diagnostics

Notice that logs are intended for root-cause analysis rather than only event accumulation:

- `BSOD-Investigator` — diagnostic reports and analysis history;
- `Vacancy-Parser-Pro/problem_logging.py` — source-specific problem context;
- `Universal-Video-Downloader/problem_log_validator.py` and `Логи проблем/` — schema and quality checks for diagnostic artifacts;
- `ZeTer-OS/problem_logs.py` — centralized problem-log layer;
- `Screen-Recorder-Pro/screen_recorder/mixins/problem_logs.py` — diagnostics inside the multimedia application lifecycle.

## 30-minute review

### A. Real-time multimedia — Screen Recorder Pro

Inspect:

- FFmpeg command construction;
- GPU/CPU capture and encoding selection;
- system audio and fallback handling;
- stopping, failure, and partially successful recording behavior;
- what `verify_project.py`, `verify_capture_recovery.py`, `verify_save_safety.py`, and `verify_recording_publication.py` actually check;
- which of those checks are executed by `.github/workflows/validate.yml`.

### B. System diagnostics — BSOD Investigator

Inspect:

- how WinDbg/CDB output becomes a diagnostic model;
- how strong signals are separated from weak signals;
- how history across independent crashes is used;
- why re-analyzing the same dump should not artificially increase confidence;
- what the safe `--self-test` validates in CI.

### C. Local AI — VoiceFlow

Inspect:

- audio → faster-whisper pipeline;
- CPU/CUDA modes;
- stable-fragment insertion without final duplication;
- behavior when the active window changes during dictation;
- Windows input fallback mechanisms;
- which parts are currently proven only by syntax/compile CI and still require real Windows runtime verification.

## How to interpret verification correctly

A green CI run does not mean a hardware-dependent feature is fully verified. The portfolio uses several evidence levels:

1. **syntax/compile** — the code parses and compiles;
2. **unit/regression** — a specific software contract is tested without external hardware;
3. **integration/self-test** — multiple components are exercised together;
4. **runtime/manual Windows verification** — requires a real window, audio device, GPU, WinAPI session, FFmpeg environment, or other runtime condition.

A technical review should match each claim to the level of evidence that actually supports it.

## Strong engineering signals

### Failure behavior

The interesting part is not only the happy path, but also behavior around a hung child process, network failure, partially created output, user cancellation, restart after interruption, and temporarily unavailable devices or tools.

### Verifiability

The repositories use GitHub Actions, `py_compile` / `compileall`, self-tests, regression tests, smoke tests, and dedicated structural / publication / recovery checks. Hardware-dependent behavior is not treated as automatically proven just because a compile step passed.

### User-data handling

Review what is excluded from Git, how settings are stored, where backup/recovery is used, how logs/caches are bounded, and which diagnostic artifacts may contain sensitive data.

### Maintainability

Newer or actively refactored projects use focused modules, `docs/`, `AGENTS.md`, explicit entrypoints, and structural checks. Large legacy modules are treated as technical debt rather than desirable architecture.

## Recurring engineering pattern

```text
external operation
    ↓
explicit state / stage
    ↓
timeout or bounded retry
    ↓
structured diagnostics
    ↓
result validation
    ↓
safe recovery or clear failure state
```

## More navigation

- [Main profile](README_EN.md)
- [Project map](PROJECTS_EN.md)
- [Engineering approach](ENGINEERING_EN.md)
- [Support and diagnostics](SUPPORT_EN.md)
