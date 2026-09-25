**Язык / Language:** [Русский](PROJECTS.md) · **English**

# Project map

This file is the extended navigation layer for the published projects. The main README gives a quick overview; this page groups the repositories by engineering area and highlights what is worth inspecting in each one.

## Web applications and browser-first products

### [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)

**Purpose:** a full browser image editor with layers, masks, history, non-destructive editing, and professional-format import/export.

**What to inspect:**

- Canvas 2D rendering/compositing pipeline;
- layers, groups, raster/vector masks, and smart objects;
- PSD/PSB import/export, including 16/32-bit typed pixel buffers;
- ICC/CMYK color-management pipeline;
- crash autosave through IndexedDB;
- regression tests and CI.

**Engineering focus:** complex browser-side graphics, precision preservation, file-format compatibility, and evolution of a large JavaScript application.

---

### [BizPilot](https://github.com/zeter1/BizPilot)

**Purpose:** a local-first workspace for small-business operations: customers, orders, deals, invoices, finance, notes, calendar, and analytics.

**What to inspect:**

- static frontend without a mandatory backend;
- local data model and persistence through `localStorage`;
- ZIP backup/restore;
- isolation of demo data from the working dataset;
- the `index.html + css/ + js/` structure.

**Engineering focus:** frontend application architecture, state management, local-first UX, and user-data safety.

## Browser 3D / WebGL

### [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)

**Purpose:** a browser 3D 5v5 FPS with the player, allied bots, and enemy AI.

**What to inspect:** modular JavaScript architecture, Three.js/WebGL, tactical/combat AI, weapons and ballistics, asset catalog, performance/recovery, and a headless browser smoke test.

**Engineering focus:** real-time browser gameplay, AI, modularizing a growing JavaScript codebase, and runtime verification.

---

### [CYBER RACE](https://github.com/zeter1/CYBER-RACE)

**Purpose:** a browser 3D combat racing game with AI opponents, weapons, pickups, and adaptive graphics quality.

**What to inspect:** Three.js/WebGL loop, AI, combat systems, Web Audio, automatic quality scaling, and WebGL context recovery.

**Engineering focus:** real-time rendering, performance adaptation, and browser game systems.

---

### [Forest Hunter](https://github.com/zeter1/ForestHunter)

**Purpose:** a browser 3D FPS with hunting, progression, loot, contracts, and AI enemies.

**What to inspect:** state-based AI, InstancedMesh, object pools, spatial collision grid, weapon systems, and progression.

**Engineering focus:** Three.js scene performance, AI/gameplay state, and managing many real-time objects.

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

1. Start with [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) — deep browser-side graphics, Canvas, and the PSD/PSB pipeline.
2. Open [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE) — Three.js/WebGL, modular JavaScript, and game AI.
3. Inspect [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) — a broad mix of Python, Windows, and multimedia engineering.
4. Open [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator) — system diagnostics and evidence handling.
5. Open [VoiceFlow](https://github.com/zeter1/VoiceFlow) — local AI and a real-time speech pipeline.
6. Open [BizPilot](https://github.com/zeter1/BizPilot) — local-first frontend application architecture.
7. Inspect [ZeTer OS](https://github.com/zeter1/ZeTer-OS) — hybrid Python/JavaScript architecture.

See also [ENGINEERING_EN.md](ENGINEERING_EN.md) for engineering principles that recur across these repositories.