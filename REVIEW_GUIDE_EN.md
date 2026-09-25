**Язык / Language:** [Русский](REVIEW_GUIDE.md) · **English**

# Technical portfolio review guide

This page provides a short route through the two main tracks of the profile: **Web Development** and **Python Development**. The goal is to move quickly from a description to code, architecture, tests, and verifiable engineering decisions.

## 5-minute review

If time is limited, open these five projects:

1. **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** — browser graphics, Canvas, PSD/PSB, high-depth pixel pipeline, masks, and color management.
2. **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** — Three.js/WebGL, modular JavaScript, tactical AI, combat systems, and browser smoke testing.
3. **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** — Python/Windows, FFmpeg, capture lifecycle, recovery, and verification scripts.
4. **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** — system diagnostics, crash dumps, WinDbg/CDB, and evidence-based analysis.
5. **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** — local AI, faster-whisper, CPU/CUDA, and Windows input.

Together they show both sides of the portfolio: complex browser runtime work and deep Python/Windows integration.

## Engineering evidence map

| What to evaluate | Project | Where to look | What it demonstrates |
|---|---|---|---|
| Browser image architecture | ZeTer Photo Editor | main app/adapter/rendering code, tests, CI | layered document model, masks, PSD/PSB, typed pixel buffers |
| WebGL/game architecture | ZAP ZONE | `src/core`, `src/weapons`, `src/combat`, `src/entities`, `src/game` | modular JavaScript, real-time loop, tactical AI |
| Local-first web state | BizPilot | `js/app.js`, storage and backup/restore flows | browser state model and user-data lifecycle |
| Multimedia recovery | Screen Recorder Pro | `screen_recorder/`, `verify_capture_recovery.py`, `verify_save_safety.py` | FFmpeg lifecycle, recovery, output safety |
| Windows diagnostics | BSOD Investigator | `bsod_investigator.py`, `docs/`, `--self-test` | crash-evidence processing and reproducible self-check |
| Local speech-to-text | VoiceFlow | `voiceflow.py`, `docs/` | faster-whisper, CPU/CUDA, Windows input |
| Long AI/multimedia workflow | Video Translator Pro | `videotranslator/`, `tests/`, `tools/`, `AGENTS.md` | checkpoints, recovery, staged processing |
| Hybrid desktop/web | ZeTer OS | `app/`, `tools/check_project.py` | Python/native bridge + modular JavaScript frontend |
| Downloader/media pipeline | Universal Video Downloader | `src/`, `tests/`, `problem_log_validator.py` | format strategy, validation, and diagnostics |

## 15-minute review

### 1. Compare Web architectures

- **ZeTer Photo Editor** — a large browser application with rendering, format adapters, masks, typed pixel data, and persistence.
- **ZAP ZONE** — a real-time Three.js application with separated runtime/gameplay modules.
- **BizPilot** — a local-first business application with no mandatory backend.
- **CYBER RACE / Forest Hunter** — compact browser games that make performance trade-offs and gameplay state easy to inspect.

### 2. Compare Python architectures

- `Screen-Recorder-Pro/screen_recorder/` — modular Windows multimedia application;
- `Universal-Video-Downloader/src/` — downloader with separate tests/scripts/docs;
- `Video-Translator-Pro/videotranslator/` — package structure for a long-running pipeline;
- `ZeTer-OS/app/` — hybrid Python + JavaScript boundary;
- `Vacancy-Parser-Pro` — scraper / GUI / logging responsibilities.

### 3. Review the verification strategy

Compare evidence levels:
1. **syntax/compile**;
2. **unit/regression**;
3. **integration/self-test**;
4. **browser smoke/runtime**;
5. **manual Windows / GPU / audio verification**.

The key rule: a claim should match the level of verification that was actually performed.

## 30-minute review

### A. Web graphics — ZeTer Photo Editor

Inspect:
- document model, layers/groups/masks;
- render state vs editable source separation;
- PSD/PSB import/export;
- 16/32-bit typed buffers;
- ICC/CMYK path;
- crash autosave;
- regression tests and CI.

### B. WebGL / AI — ZAP ZONE

Inspect:
- engine / weapons / combat / entities / progression / runtime boundaries;
- tactical AI;
- ballistics and weapon handling;
- browser boot smoke test;
- performance/recovery contracts.

### C. Windows multimedia — Screen Recorder Pro

Inspect:
- FFmpeg command construction;
- capture/encoding selection;
- child-process lifecycle;
- capture recovery;
- save safety;
- what GitHub Actions actually execute.

### D. System diagnostics — BSOD Investigator

Inspect:
- how dump/Event Log/driver data become an evidence model;
- how strong and weak signals are separated;
- history across independent crashes;
- safe self-test.

### E. Local AI — VoiceFlow

Inspect:
- audio → faster-whisper pipeline;
- CPU/CUDA paths;
- stable-fragment insertion;
- Windows input fallbacks;
- the boundary between CI-verifiable and hardware/runtime-dependent behavior.

## Strong signals to look for

**Web:** state lifecycle, rendering budgets, module boundaries, graceful degradation, persistence, browser smoke tests.

**Python:** process lifecycle, WinAPI integration, recovery, external-tool validation, structured diagnostics.

**Across both:** tests, CI, documentation, constrained change scope, and honest labeling of what is not yet verified.

## More navigation

- [Main profile](README_EN.md)
- [Project map](PROJECTS_EN.md)
- [Engineering approach](ENGINEERING_EN.md)
- [Support and diagnostics](SUPPORT_EN.md)
