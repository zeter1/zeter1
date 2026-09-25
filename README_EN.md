**Язык / Language:** [Русский](README.md) · **English**

# Dmitry Kolesnichenko

### Python Developer · Web Developer

I build **web applications and browser-first products** with HTML/CSS/JavaScript, Canvas/WebGL, and Three.js, alongside **Python applications for Windows**, automation tools, multimedia systems, and local AI software.

My portfolio has two primary tracks: **Web Development** and **Python Development**. In both, I focus on architecture, diagnostics, failure recovery, automated verification, and user-data safety—not only feature delivery.

## Main areas

| Area | What I build | Technologies |
|---|---|---|
| **Web Development** | browser applications, local-first interfaces, image editors, 2D/3D applications and games | JavaScript, HTML/CSS, Canvas 2D, WebGL, Three.js, Web Audio API, IndexedDB, localStorage |
| **Python Development** | Windows desktop software, automation, system utilities, multimedia, local AI | Python, Tkinter, WinAPI, ctypes, COM/SAPI, SQLite, FFmpeg, Whisper, CUDA |
| **Hybrid Desktop/Web** | desktop applications with JavaScript UI and a Python/native bridge | Python, pywebview, JavaScript, local-first state, backup/recovery |

## All projects

Below are **all 14 project repositories** on my GitHub profile. The `zeter1/zeter1` profile repository is not counted as a separate product because it hosts the portfolio itself.

| Project | Area | What it demonstrates |
|---|---|---|
| **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** | Web / Graphics | browser image editor: Canvas 2D, layers/masks, PSD/PSB, high-depth pixel pipeline, ICC/CMYK, regression tests |
| **[BizPilot](https://github.com/zeter1/BizPilot)** | Web / Application | local-first business app, state model, localStorage, ZIP backup/restore, frontend without a mandatory backend |
| **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** | Web / 3D | Three.js/WebGL FPS, modular JavaScript, tactical AI, weapons/ballistics, structural validation, browser smoke CI |
| **[CYBER RACE](https://github.com/zeter1/CYBER-RACE)** | Web / 3D | browser 3D combat racing, AI opponents, weapons, Web Audio, adaptive quality, WebGL recovery |
| **[Forest Hunter](https://github.com/zeter1/ForestHunter)** | Web / 3D | browser FPS with hunting, AI, progression, InstancedMesh, object pools, and spatial collisions |
| **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** | Python / Windows | FFmpeg, Desktop Duplication, NVENC, WinAPI, process lifecycle, capture recovery, save safety |
| **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** | Python / Diagnostics | WinDbg/CDB, crash dumps, Event Log, SQLite, and evidence-based diagnostics |
| **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** | Python / AI | local speech-to-text, faster-whisper, CPU/CUDA, background pipeline, Windows input |
| **[Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)** | Python / AI + Multimedia | Whisper → translation → TTS → FFmpeg, checkpoints, cache, recovery, artifact validation |
| **[Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)** | Python / Automation | multi-source vacancy parsing, adapters, fault isolation, deduplication, Excel export |
| **[Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)** | Python / Multimedia | yt-dlp, MP4/MP3, format selection, remux/transcoding fallback, ffprobe validation, tests |
| **[Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)** | Python / Windows | Microsoft SAPI/COM, Windows TTS, MP3, global hotkeys, state persistence, long-job recovery |
| **[Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)** | Python / Windows | WinAPI, WTS API, mutex, power management, self-test, bounded logging |
| **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** | Hybrid Desktop/Web | Python + JavaScript, pywebview bridge, modular frontend, local-first state, backup/recovery |

Extended technical map of all projects: **[PROJECTS_EN.md](PROJECTS_EN.md)**.

## Engineering approach

- Find root causes instead of hiding symptoms.
- Separate responsibilities as projects grow.
- Verify the result, not only the code.
- Design long-running workflows for recovery.
- Treat user data and local state as architectural concerns.
- Verify AI-assisted changes with the same discipline as regular code.

More detail: **[ENGINEERING_EN.md](ENGINEERING_EN.md)**.

## Verifiable entry points

A technical reviewer can jump directly from the profile to code and checks:

- **ZeTer Photo Editor:** [`src/adapters/`](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters) · [`tests/color-management.test.mjs`](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs) · [CI](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/.github/workflows/ci.yml).
- **ZAP ZONE:** [`src/core/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/core) · [`src/combat/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/combat) · [`src/weapons/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/weapons) · [structural validation](https://github.com/zeter1/ZAP-ZONE/blob/main/scripts/validate-structure.mjs) · [browser smoke CI](https://github.com/zeter1/ZAP-ZONE/blob/main/.github/workflows/validate.yml).
- **BizPilot:** [`js/app.js`](https://github.com/zeter1/BizPilot/blob/main/js/app.js) · [static/local-asset validation CI](https://github.com/zeter1/BizPilot/blob/main/.github/workflows/validate.yml) · [security policy](https://github.com/zeter1/BizPilot/blob/main/SECURITY.md).
- **CYBER RACE:** [`index.html`](https://github.com/zeter1/CYBER-RACE/blob/main/index.html) · [inline-JS/static-server CI](https://github.com/zeter1/CYBER-RACE/blob/main/.github/workflows/validate.yml) · [security policy](https://github.com/zeter1/CYBER-RACE/blob/main/SECURITY.md).
- **Forest Hunter:** [`index.html`](https://github.com/zeter1/ForestHunter/blob/main/index.html) · [inline-JS/static-server CI](https://github.com/zeter1/ForestHunter/blob/main/.github/workflows/validate.yml) · [security policy](https://github.com/zeter1/ForestHunter/blob/main/SECURITY.md).
- **Screen Recorder Pro:** [`screen_recorder/`](https://github.com/zeter1/Screen-Recorder-Pro/tree/main/screen_recorder) · [capture recovery](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_capture_recovery.py) · [save safety](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_save_safety.py).
- **BSOD Investigator:** [`bsod_investigator.py`](https://github.com/zeter1/BSOD-Investigator/blob/main/bsod_investigator.py) · [`docs/`](https://github.com/zeter1/BSOD-Investigator/tree/main/docs).
- **VoiceFlow:** [`voiceflow.py`](https://github.com/zeter1/VoiceFlow/blob/main/voiceflow.py) · [`docs/`](https://github.com/zeter1/VoiceFlow/tree/main/docs).

## Technologies

**Web:** `HTML` · `CSS` · `JavaScript` · `Canvas 2D` · `WebGL` · `Three.js` · `Web Audio API` · `IndexedDB` · `localStorage`

**Python / Windows:** `Python` · `Tkinter` · `WinAPI` · `ctypes` · `COM / SAPI` · `pywebview` · `PyInstaller`

**AI / Multimedia:** `FFmpeg` · `FFprobe` · `yt-dlp` · `Whisper` · `faster-whisper` · `CUDA` · `Edge TTS`

**Data / Automation:** `SQLite` · `JSON` · `pandas` · `openpyxl` · `requests` · `BeautifulSoup`

**Engineering:** `Git` · `GitHub Actions` · regression tests · smoke tests · diagnostics · backup/recovery

## Navigation

- **[PROJECTS_EN.md](PROJECTS_EN.md)** — project map.
- **[REVIEW_GUIDE_EN.md](REVIEW_GUIDE_EN.md)** — 5/15/30-minute technical review path.
- **[ENGINEERING_EN.md](ENGINEERING_EN.md)** — engineering principles and examples.
- **[SUPPORT_EN.md](SUPPORT_EN.md)** — diagnostics and bug-report guidance for Web, Python, and hybrid projects.

## Contacts

- **Email:** zeter11@gmail.com
- **Telegram:** https://t.me/zeter1
- **LinkedIn:** https://www.linkedin.com/in/zeter/
- **Website / portfolio:** https://dkl.do.am/
