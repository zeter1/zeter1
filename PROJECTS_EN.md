**Язык / Language:** [Русский](PROJECTS.md) · **English**

[Profile](README_EN.md) · [Applications](USER_GUIDE_EN.md) · [Technical review](REVIEW_GUIDE_EN.md) · [Support](SUPPORT_EN.md)

# Project map

This page maps the projects and engineering decisions available for code review. The main areas are **Web Development** and **Python Development**, with hybrid applications and a new video editor listed separately. For choosing, downloading, and running a program, use the **[user catalog](USER_GUIDE_EN.md)**.

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

**Engineering focus:** Three.js/WebGL loop, Web Audio, AI, combat systems, performance adaptation, and WebGL context recovery. Opponent frame/attack and homing kinematics now run through dependency-injected simulation contracts. `tests/scenarios.mjs` replays 180 seeded AI frames, attack decisions, and 90 homing-rocket frames before the headless WebGL integration gate.

---

### [Forest Hunter](https://github.com/zeter1/ForestHunter)

**What it is:** a browser 3D FPS with hunting, progression, loot, contracts, and AI enemies.

**Engineering focus:** state-based AI, InstancedMesh, object pools, spatial collision grid, and real-time entities. Boar state transitions, stochastic damage rolls, reload/deployable timelines, and hit ordering are now replayable contracts with injected RNG. Seeded fixtures validate 150 AI frames and combat timelines before the headless WebGL integration gate; pointer lock, Web Audio, and real GPU behavior remain separate proof layers.

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

### [ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter)

**What it is:** a Windows utility that converts video courses to per-lesson MP3 and sequential audio parts up to 10 hours long, and merges videos into MP4 parts.

**What to inspect:** Tkinter UI, `videovaudio/audio/`, `videovaudio/video/`, `process_runner.py` (FFmpeg lifecycle, cancellation, and timeouts), `diagnostics/`, `tools/test_audio_regressions.py`, [Windows EXE CI](https://github.com/zeter1/ZeTer-Media-Converter/blob/main/.github/workflows/build-windows.yml).

**Engineering focus:** verified previous-MP3 backups with a manifest, staged output validation, structured diagnostics, and standalone packaging with SHA-256 verification. [v3.3.5 release](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5). Full GUI and multi-hour processing require manual testing.

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

## Desktop / Video

### [Zeter Video Editor](https://github.com/zeter1/zeter-video-editor)

**What it is:** a Windows multi-track video editor with local projects, built with Tauri, React, TypeScript, Rust, and FFmpeg.

**What to inspect:** [README](https://github.com/zeter1/zeter-video-editor#readme), [PROJECT_STATUS.md](https://github.com/zeter1/zeter-video-editor/blob/main/PROJECT_STATUS.md), and [package.json](https://github.com/zeter1/zeter-video-editor/blob/main/apps/desktop/package.json). The project is undergoing release-readiness work; there is no public GitHub release yet. PROJECT_STATUS.md owns the current implementation and verification status.

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
