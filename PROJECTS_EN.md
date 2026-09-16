**Язык / Language:** [Русский](PROJECTS.md) · **English**

# Project map

This file is the extended navigation layer for the published projects. The main README gives a quick overview; this page groups the repositories by engineering area and highlights what is worth inspecting in each one.

## Windows and system integration

### [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)

**Purpose:** investigate Windows BSOD causes using crash dumps, Windows Event Log, driver metadata, and history from previous failures.

**What to inspect:**

- Microsoft CDB / WinDbg integration;
- the model that evaluates suspect drivers from multiple evidence sources;
- separation between evidence strength and telemetry quality;
- SQLite history, crash fingerprints, and protection from counting the same crash twice;
- self-test and CI;
- work with UAC, protected system files, and diagnostic bundles.

**Engineering focus:** root-cause diagnostics, careful handling of uncertainty, and preserving context for repeated analysis.

---

### [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)

**Purpose:** lock Windows safely while optionally preventing sleep so background work can continue.

**What to inspect:**

- `LockWorkStation`, `SetThreadExecutionState`, WTS API;
- single-instance protection through a mutex;
- lifecycle of the sleep-prevention mode;
- safe self-test;
- compact logging with size and retention limits.

**Engineering focus:** WinAPI through `ctypes`, system state, and careful behavior of a background utility.

---

### [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)

**Purpose:** read text with Windows system voices and create MP3 files from large texts.

**What to inspect:**

- Microsoft SAPI and COM;
- global hotkeys;
- state persistence across multiple tabs;
- recovery for long conversion jobs;
- FFmpeg and Windows-audio integration.

**Engineering focus:** Windows desktop, state persistence, and recovery of long-running operations.

## Multimedia

### [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)

**Purpose:** capture the screen, microphone, and system audio, create screenshots, and work with annotations.

**What to inspect:**

- FFmpeg Desktop Duplication (`ddagrab`);
- GPU pipeline and NVIDIA NVENC;
- CoreAudio loopback fallback;
- child FFmpeg process management;
- modular `screen_recorder/` structure;
- dedicated verification scripts for capture recovery, save safety, and publication flow;
- timing and smoothness diagnostics.

**Engineering focus:** real-time multimedia, process management, fallback strategies, and regression protection for a complex desktop application.

---

### [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)

**Purpose:** recognize speech in video, translate it, synthesize a new voice track, and assemble the final video.

**What to inspect:**

- Whisper → translation → TTS → FFmpeg pipeline;
- Pause Sync for translated phrases that become longer than the source;
- checkpoint/recovery;
- persistent TTS cache;
- bounded retries and protection against cascading network failures;
- final MP4 validation.

**Engineering focus:** long multi-stage workflows, recovery after failure, and verification of the final artifact rather than only a successful process exit.

---

### [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)

**Purpose:** produce a convenient MP4 up to 1080p or MP3 from sites supported by yt-dlp.

**What to inspect:**

- yt-dlp format selection;
- `compatible streams → lossless remux → transcoding fallback` strategy;
- result validation through ffprobe;
- modular structure;
- `docs/CODE_MAP.md` and tools that identify the smallest code scope for a change.

**Engineering focus:** media compatibility, avoiding unnecessary transcoding, and maintainability.

## Speech / AI

### [VoiceFlow](https://github.com/zeter1/VoiceFlow)

**Purpose:** local speech-to-text directly into the active field of any Windows application.

**What to inspect:**

- faster-whisper;
- CPU/CUDA execution paths;
- streaming handling of stable speech fragments;
- switching between active windows while dictating;
- native text insertion and fallback mechanisms;
- separated diagnostics for hotkeys / capture / inference / insertion;
- privacy-first design: transcription runs locally after the model is downloaded.

**Engineering focus:** real-time pipelines, local ML inference, Windows input automation, and concurrent background work.

## Hybrid desktop/web applications

### [ZeTer OS](https://github.com/zeter1/ZeTer-OS)

**Purpose:** a local workspace combining notes, tasks, calendar, files, spreadsheets, and other utilities.

**What to inspect:**

- Python desktop shell + pywebview;
- native bridge between Python and JavaScript;
- modular frontend;
- local-first state model;
- backups and restore points;
- portable release pipeline;
- structural checks and JavaScript smoke tests.

**Engineering focus:** boundaries between frontend/native layers, user-data handling, and architecture of a growing application.

## Network, parsing, and data

### [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)

**Purpose:** collect vacancies from multiple sources, filter and deduplicate them, and export the result.

**What to inspect:**

- separate source adapters;
- isolation of one site's failure from the overall search session;
- local filtering and deduplication;
- Excel export;
- structured diagnostic sessions;
- offline regression tests for parser logic.

**Engineering focus:** unstable external sources, fault isolation, and observability of a network workflow.

## How to review the portfolio

If time is limited:

1. Start with [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) — the broadest mix of Windows and multimedia engineering.
2. Open [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator) — system diagnostics and evidence handling.
3. Open [VoiceFlow](https://github.com/zeter1/VoiceFlow) — local AI and a real-time speech pipeline.
4. Open [ZeTer OS](https://github.com/zeter1/ZeTer-OS) — hybrid Python/JavaScript architecture.
5. For reliability of long-running workflows, inspect [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro).

See also [ENGINEERING_EN.md](ENGINEERING_EN.md) for engineering principles that recur across these repositories.