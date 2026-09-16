**Язык / Language:** [Русский](README.md) · **English**

# Dmitry Kolesnichenko

### Python Developer · Windows/Desktop · Automation · Multimedia · AI-assisted development

I build practical Windows applications, automation tools, multimedia software, local AI utilities, and hybrid desktop systems.

I try to take projects beyond a working prototype: separating responsibilities, adding diagnostics and recovery, automating verification, protecting user data, and documenting the codebase so it can be understood without reading every source file.

## Quick navigation

- **[PROJECTS.md](PROJECTS.md)** — detailed project map: what each project solves and which engineering decisions are worth reviewing.
- **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)** — a 5-, 15-, or 30-minute technical review path with concrete files and checks.
- **[ENGINEERING.md](ENGINEERING.md)** — my engineering approach to reliability, diagnostics, recovery, testing, and AI-assisted development.
- **[SUPPORT.md](SUPPORT.md)** — guidance for useful bug reports and diagnostic data across projects.

For a fast view of my technical range, start with **Screen Recorder Pro → BSOD Investigator → VoiceFlow → ZeTer OS → Video Translator Pro**.

## Core specialization

- **Python / Windows desktop** — Tkinter, WinAPI, ctypes, COM/SAPI, system tray, global hotkeys, startup integration, and Windows-specific tooling.
- **Multimedia** — FFmpeg, FFprobe, yt-dlp, screen capture, audio/video processing, remux/transcoding, and NVENC hardware encoding.
- **Speech / AI** — Whisper, faster-whisper, Edge TTS, local speech recognition, and CPU/CUDA pipelines.
- **Automation and data** — SQLite, JSON, pandas, openpyxl, requests, BeautifulSoup, exports, and local workflows.
- **Hybrid applications** — Python + pywebview + HTML/CSS/JavaScript, native bridges, and local state storage.
- **Reliability** — timeouts, retry strategies, checkpoint/recovery, subprocess management, backups, structured logs, and self-tests.
- **AI-assisted engineering** — I use ChatGPT and Codex to accelerate analysis and refactoring, while validating changes with tests, static checks, and manual runtime verification where required.

## Projects

| Project | Purpose | Key engineering topics |
|---|---|---|
| **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** | Screen, system-audio, microphone, and screenshot capture | FFmpeg, Desktop Duplication, NVENC, WinAPI hotkeys, process management, modular architecture |
| **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** | Investigating Windows BSOD causes | WinDbg/CDB, crash dumps, Event Log, driver analysis, SQLite, evidence-based diagnostics |
| **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** | Local voice input for any Windows application | faster-whisper, CUDA/CPU, real-time pipeline, Windows input, background tasks, privacy-first design |
| **[Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)** | Speech recognition, translation, and voice-over for video | Whisper, TTS, FFmpeg, checkpoints, recovery, caching, resilient long-running pipelines |
| **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** | Local workspace for notes, tasks, files, and utilities | Python + JavaScript, pywebview bridge, local-first data, backup/recovery, modular frontend |
| **[Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)** | Aggregating vacancies from multiple sources | HTTP/parsing, source adapters, filtering, deduplication, Excel, fault isolation |
| **[Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)** | Video/audio downloading with compatibility-first output | yt-dlp, FFmpeg/ffprobe, MP4 up to 1080p, remux/transcoding fallback, diagnostics |
| **[Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)** | Text-to-speech and MP3 creation | Microsoft SAPI, COM, global hotkeys, recovery for long-running jobs |
| **[Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)** | Lock Windows without interrupting long-running background tasks | WinAPI, WTS API, power management, mutex, compact diagnostics |

## Engineering evidence

I try to separate engineering claims from the evidence supporting them. These are useful entry points for technical review.

| Engineering area | Where to look | What it demonstrates |
|---|---|---|
| **Recovery and result safety** | `Screen-Recorder-Pro/verify_capture_recovery.py`, `verify_save_safety.py`, `screen_recorder/` | behavior around FFmpeg failures, stopping, and partially created output |
| **Regression / structural verification** | `Screen-Recorder-Pro/verify_project.py`, `Universal-Video-Downloader/tests/`, `Vacancy-Parser-Pro/tests/` | real automated checks rather than only manual smoke testing |
| **Evidence-based diagnostics** | `BSOD-Investigator`, `Vacancy-Parser-Pro/problem_logging.py`, `Universal-Video-Downloader/problem_log_validator.py` | how diagnostic context becomes a reproducible investigation |
| **Local AI pipeline** | `VoiceFlow/voiceflow.py`, `Video-Translator-Pro/videotranslator/` | CPU/CUDA paths, speech-to-text, staged processing, and recovery |
| **Hybrid desktop/web architecture** | `ZeTer-OS/app/`, `tools/check_project.py` | native bridge, frontend modules, and project-level verification |
| **CI and safe automation** | `.github/workflows/` across the main repositories | compile/test/self-test gates, Windows runners, external-tool validation |

For a detailed route through specific files and evidence levels, see **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)**.

## Competency map by repository

| Area | Projects |
|---|---|
| **Windows API and system integration** | Screen Recorder Pro, BSOD Investigator, VoiceFlow, Windows PC Locker, Text to MP3 |
| **Multimedia pipelines** | Screen Recorder Pro, Video Translator Pro, Universal Video Downloader, Text to MP3 |
| **Local AI / Speech** | VoiceFlow, Video Translator Pro |
| **Long-running and fault-tolerant tasks** | Video Translator Pro, Screen Recorder Pro, Text to MP3 |
| **Diagnostics and root-cause analysis** | BSOD Investigator, Screen Recorder Pro, Vacancy Parser Pro, Windows PC Locker |
| **Parsing and network integrations** | Vacancy Parser Pro, Universal Video Downloader |
| **Desktop + Web architecture** | ZeTer OS |
| **Automated verification and CI** | Several projects include GitHub Actions, self-tests, smoke tests, or project-specific verification scripts |

## What can be evaluated in my repositories

**More than the happy path.** Applications explicitly handle timeouts, cancellation, external-process failures, network errors, and recovery after interruption.

**Diagnostics for real failures.** Complex applications produce structured diagnostic data intended to reveal root causes instead of accumulating large, unstructured logs.

**Architecture designed for change.** Large applications are progressively split into focused modules, with documented responsibility boundaries and structural checks where the codebase evolves actively.

**User-data handling.** Local state, backups, recovery, and keeping runtime data out of Git are treated as part of the application design.

**Verification.** I use syntax checks, self-tests, regression tests, smoke tests, and CI. Hardware-dependent scenarios are additionally validated manually on Windows.

More detail: **[engineering approach and examples](ENGINEERING.md)**.

## How to review the projects quickly

The README of each main repository includes:

1. purpose and core features;
2. installation instructions;
3. launch command;
4. step-by-step usage;
5. architecture or notable engineering decisions;
6. diagnostics, reliability, or limitations.

Larger projects also use `docs/`, code maps, verification scripts, tests, and CI configurations for deeper review.

## Development approach

**Start with the user problem, then choose the technology.** Architecture and UI should help solve the task rather than demonstrate complexity for its own sake.

**Find root causes instead of hiding symptoms.** For difficult failures, I add diagnostic context, reproducible steps, and compact structured logs.

**Long-running operations should survive real-world failures.** I use checkpoints, bounded retries, timeouts, safe process termination, and recovery of intermediate results.

**Code should be easy to change next time.** I split large applications into responsibility areas, document architectural contracts, and add automated regression checks.

**AI is an accelerator, not a substitute for engineering verification.** AI-assisted changes are validated with the same discipline as any other code changes.

## Technologies

`Python` · `Tkinter` · `WinAPI` · `ctypes` · `COM / SAPI` · `FFmpeg` · `FFprobe` · `yt-dlp` · `Whisper` · `faster-whisper` · `CUDA` · `Edge TTS` · `SQLite` · `pandas` · `openpyxl` · `requests` · `BeautifulSoup` · `pywebview` · `HTML` · `CSS` · `JavaScript` · `Git` · `GitHub Actions` · `PyInstaller`

## About me

I have built more than 23 software projects. My main areas are practical Windows applications, automation, multimedia, system utilities, and software that combines desktop development with modern AI capabilities.

I am interested in the full lifecycle of an application: from idea and first working prototype to refactoring, diagnosis of real failures, UX improvement, testing, and preparation for long-term maintenance.

## Contacts

- **Email:** zeter11@gmail.com
- **Telegram:** https://t.me/zeter1
- **LinkedIn:** https://www.linkedin.com/in/zeter/
- **Website / portfolio:** https://dkl.do.am/
