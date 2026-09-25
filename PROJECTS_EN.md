**Язык / Language:** [Русский](PROJECTS.md) · **English**

# Project map

This page covers **all 14 project repositories** on the profile (excluding the `zeter1/zeter1` portfolio repository). The portfolio has two main tracks — **Web Development** and **Python Development**. This page is not just a repository list; it highlights the engineering decisions worth inspecting in each project.

## Web Development

### [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)

**What it is:** a browser image editor with layers, masks, history, non-destructive editing, and a PSD/PSB pipeline.

**What to inspect:** Canvas 2D rendering/compositing, layers/groups, raster/vector masks, smart objects, PSD/PSB import/export, typed 16/32-bit pixel buffers, ICC/CMYK pipeline, IndexedDB crash autosave, regression tests, and CI.

**Engineering focus:** complex browser-side graphics, precision preservation, format compatibility, and evolution of a large JavaScript application.

---

### [BizPilot](https://github.com/zeter1/BizPilot)

**What it is:** a local-first workspace for customers, orders, deals, invoices, finance, notes, calendar, and analytics.

**What to inspect:** static frontend without a mandatory backend, state model, `localStorage`, ZIP backup/restore, demo-data isolation, `js/cashflow.js`, cash-flow regression tests, and a real headless Chrome startup smoke. That smoke exposed a latent `cashflowForecast is not defined` startup failure; the root cause was fixed and covered by regression tests.

---

### [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)

**What it is:** a browser 3D 5v5 FPS with allied and enemy AI bots.

**What to inspect:** modular `src/`, Three.js/WebGL runtime, tactical/combat AI, weapon handling and ballistics, asset catalog, performance/recovery, and headless browser smoke testing.

---

### [CYBER RACE](https://github.com/zeter1/CYBER-RACE)

**What it is:** a browser 3D combat racing game with AI opponents, weapons, pickups, and adaptive quality.

**Engineering focus:** Three.js/WebGL loop, Web Audio, AI, combat systems, performance adaptation, and WebGL context recovery. The first architecture pass moved the giant inline runtime into `src/core`, `src/game`, `src/ai`, `src/weapons`, `src/audio`, and `src/ui`; structural validation and a headless WebGL boot are green in Actions.

---

### [Forest Hunter](https://github.com/zeter1/ForestHunter)

**What it is:** a browser 3D FPS with hunting, progression, loot, contracts, and AI enemies.

**Engineering focus:** state-based AI, InstancedMesh, object pools, spatial collision grid, and real-time object management. The first architecture pass introduced core/game/ai/weapons/audio/ui boundaries; structural validation and headless WebGL boot are green while interactive gameplay/GPU behavior remains a separate proof layer.

## Python Development

### [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)

**What it is:** a Windows application for screen, system-audio, microphone, and screenshot capture.

**What to inspect:** FFmpeg Desktop Duplication, NVENC, CoreAudio loopback fallback, child-process lifecycle, modular `screen_recorder/`, capture recovery, save safety, and project verification.

---

### [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)

**What it is:** a BSOD investigation tool built around crash dumps, Event Log data, and driver information.

**What to inspect:** CDB/WinDbg, evidence model, crash fingerprints, SQLite history, self-test, and CI.

---

### [VoiceFlow](https://github.com/zeter1/VoiceFlow)

**What it is:** local speech-to-text for inserting text into the active field of a Windows application.

**What to inspect:** faster-whisper, CPU/CUDA paths, background pipeline, Windows input, and diagnostics.

---

### [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)

**What it is:** a Whisper → translation → TTS → FFmpeg pipeline for translating and re-voicing video.

**What to inspect:** checkpoints, persistent cache, bounded retry, recovery, and final artifact validation.

---

### [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)

**What it is:** multi-source vacancy aggregation with filtering, deduplication, and Excel export.

**What to inspect:** source adapters, fault isolation, normalization/deduplication, and offline regression tests.

---

### [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)

**What it is:** MP4/MP3 downloading with a compatibility-first strategy.

**What to inspect:** yt-dlp format selection, remux/transcoding fallback, ffprobe validation, modular `src/`, tests, and code map.

---

### [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)

**What it is:** Windows TTS + MP3 creation.

**What to inspect:** Microsoft SAPI/COM, global hotkeys, state persistence, and long-job recovery.

---

### [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)

**What it is:** a Windows utility for workstation locking and sleep-state control.

**What to inspect:** WinAPI, WTS API, mutex, power management, self-test, and bounded logging.

## Hybrid Desktop/Web

### [ZeTer OS](https://github.com/zeter1/ZeTer-OS)

**What it is:** a local workspace with a Python desktop shell and JavaScript frontend.

**What to inspect:** pywebview bridge, modular frontend, local-first state, backup/recovery, and project-level verification.

## How to review the portfolio

If time is limited:
1. **ZeTer Photo Editor** — deep browser-side engineering.
2. **ZAP ZONE** — WebGL, modular JavaScript, and AI.
3. **Screen Recorder Pro** — Python/Windows/multimedia and recovery.
4. **BSOD Investigator** — diagnostics and evidence handling.
5. **VoiceFlow** — local AI.
6. **BizPilot** — local-first web architecture.
7. **ZeTer OS** — hybrid Python + JavaScript.

For concrete entry points and verification levels, see **[REVIEW_GUIDE_EN.md](REVIEW_GUIDE_EN.md)**.
