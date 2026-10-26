**Язык / Language:** [Русский](README.md) · **English**

# Dmitry Kolesnichenko

### Python Developer · Web Developer

I build **web applications and browser-first products** with HTML/CSS/JavaScript, Canvas/WebGL, and Three.js, alongside **Python applications for Windows**, automation tools, multimedia systems, and local AI software.

Choose a tool for your task, find its setup instructions, or inspect how it is built. My main areas are **Web Development** and **Python Development**: browser tools and games, Windows applications, automation, and multimedia.

**For users:** [choose, download, and get started](USER_GUIDE_EN.md). **For employers:** [a 5/15/30-minute route through code, architecture, and checks](REVIEW_GUIDE_EN.md). **Portfolio and web demos:** [visit website](https://dkl.do.am/).

On this page: [choose an application](#what-would-you-like-to-do) · [inspect engineering decisions](#for-employers-and-technical-reviewers) · [all projects](#all-projects).

**Discuss a role or project:**

- [https://t.me/zeter1](https://t.me/zeter1)
- [zeter11@gmail.com](mailto:zeter11@gmail.com)

**Report a bug:** [prepare a useful report](SUPPORT_EN.md).

## What would you like to do?

| Task | Project | Start here |
|---|---|---|
| Edit images and work with layers | [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) | [Try online](https://dkl.do.am/servisi/PhotoEditor/index.html) · [Get started](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/README_EN.md#get-started) |
| Manage clients, tasks, and business finances | [BizPilot](https://github.com/zeter1/BizPilot) | [Launch online](https://dkl.do.am/portfolio/bizpilot/index.html) · [Instructions](https://github.com/zeter1/BizPilot/blob/main/README_EN.md#get-started) |
| Record the screen and audio or take screenshots | [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) | [Windows builds](https://github.com/zeter1/Screen-Recorder-Pro/releases) |
| Dictate text instead of typing | [VoiceFlow](https://github.com/zeter1/VoiceFlow) | [Windows builds](https://github.com/zeter1/VoiceFlow/releases) |
| Translate and voice over videos | [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro) | [Windows builds](https://github.com/zeter1/Video-Translator-Pro/releases) |
| Download MP4 videos up to 1080p and extract MP3 audio | [ZeTer Video Downloader](https://github.com/zeter1/ZeTer-Video-Downloader) | [Windows builds](https://github.com/zeter1/ZeTer-Video-Downloader/releases) |
| Convert a video course to MP3 or merge video in up-to-10-hour parts | [ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter) | [Download Windows EXE v3.3.5](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5) |
| Collect vacancies and export them to Excel | [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro) | [Windows builds](https://github.com/zeter1/Vacancy-Parser-Pro/releases) |
| Organize notes and tasks | [ZeTer OS](https://github.com/zeter1/ZeTer-OS) | [Launch online](https://dkl.do.am/zeteros/index.html) · [Windows builds](https://github.com/zeter1/ZeTer-OS/releases) |
| Play browser games | [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE), [CYBER RACE](https://github.com/zeter1/CYBER-RACE), [Forest Hunter](https://github.com/zeter1/ForestHunter) | [Startup and requirements](USER_GUIDE_EN.md#browser-applications-and-games) |

**Before downloading a Windows application:** open that project's Releases page and check whether the build is a regular release or marked **Pre-release**. **ZeTer Media Converter v3.3.5** has a regular [Windows EXE release](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5). Other apps may require FFmpeg, an AI model, drivers, or an external service; check the project's README for requirements. The full user catalog, including video downloads, text-to-speech, and Windows diagnostics, is in **[USER_GUIDE_EN.md](USER_GUIDE_EN.md)**.

**Safety check before running a download:** get installers only from the linked repository's **Releases** page; check the publisher, version, and system requirements. If a release has no digital signature or published checksum, do not treat its binary provenance as cryptographically verified. Do not disable SmartScreen/antivirus just to run an app, and do not run unverified EXEs as administrator.

## For employers and technical reviewers

Three starting points connect a user's task to an engineering decision and its check:

| Project and task | Engineering decision | What to inspect |
|---|---|---|
| **BizPilot** — plan small-business cash flow | Financial calculations are separate from the UI; tests cover overdue invoices and a negative balance. | [Calculation module](https://github.com/zeter1/BizPilot/blob/main/js/cashflow.js) · [regression scenarios](https://github.com/zeter1/BizPilot/blob/main/scripts/test-cashflow.mjs) · [CI results](https://github.com/zeter1/BizPilot/actions) |
| **Screen Recorder Pro** — record a screen and save the result | FFmpeg process management, capture recovery, and protection of existing files during saving. | [Application modules](https://github.com/zeter1/Screen-Recorder-Pro/tree/main/screen_recorder) · [save-safety checks](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_save_safety.py) · [CI results](https://github.com/zeter1/Screen-Recorder-Pro/actions) |
| **ZeTer Photo Editor** — edit layered images | Graphics-format adapters and separate color-management checks. | [Adapters](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters) · [color scenarios](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs) · [CI results](https://github.com/zeter1/ZeTer-Photo-Editor/actions) |

For other areas and a deeper review, follow the **[5/15/30-minute route](REVIEW_GUIDE_EN.md)**. The “CI results” links open **GitHub Actions** runs: match the branch, commit, and checks performed. A green run for a different revision does not verify the current code or a downloaded build.

I use ChatGPT/Codex during development, with diff review, automated checks, and manual scenarios where browser, Windows, or hardware behavior matters. Tests in a repository do not establish that every user workflow works on every computer.

## Main areas

| Area | What I build | Technologies |
|---|---|---|
| **Web Development** | browser applications, local-first interfaces, image editors, 2D/3D applications and games | JavaScript, HTML/CSS, Canvas 2D, WebGL, Three.js, Web Audio API, IndexedDB, localStorage |
| **Python Development** | Windows desktop software, automation, system utilities, multimedia, local AI | Python, Tkinter, WinAPI, ctypes, COM/SAPI, SQLite, FFmpeg, Whisper, CUDA |
| **Hybrid Desktop/Web** | desktop applications with JavaScript UI and a Python/native bridge | Python, pywebview, JavaScript, local-first state, backup/recovery |

## All projects

The following projects expose their code and engineering decisions. User-facing setup instructions are collected separately in **[USER_GUIDE_EN.md](USER_GUIDE_EN.md)**.

| Project | Area | What it demonstrates |
|---|---|---|
| **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** | Web / Graphics | browser image editor: Canvas 2D, layers/masks, PSD/PSB, high-depth pixel pipeline, ICC/CMYK, regression tests |
| **[BizPilot](https://github.com/zeter1/BizPilot)** | Web / Application | local-first business app, testable cash-flow engine, localStorage/ZIP backup, regression tests, real headless-browser boot smoke |
| **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** | Web / 3D | Three.js/WebGL FPS, modular JavaScript, tactical AI, weapons/ballistics, structural validation, browser smoke CI |
| **[CYBER RACE](https://github.com/zeter1/CYBER-RACE)** | Web / 3D | Three.js/WebGL combat racing; dependency-injected opponent/ballistics simulation, seeded replay fixtures, Node contracts, and headless WebGL integration CI |
| **[Forest Hunter](https://github.com/zeter1/ForestHunter)** | Web / 3D | Three.js FPS; replayable boar state machine, seeded combat/reload/deployable scenarios, environment modules, Node contracts, and headless WebGL CI |
| **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** | Python / Windows | FFmpeg, Desktop Duplication, NVENC, WinAPI, process lifecycle, capture recovery, save safety |
| **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** | Python / Diagnostics | WinDbg/CDB, crash dumps, Event Log, SQLite, and evidence-based diagnostics |
| **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** | Python / AI | local speech-to-text, faster-whisper, CPU/CUDA, background pipeline, Windows input |
| **[Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)** | Python / AI + Multimedia | Whisper → translation → TTS → FFmpeg, checkpoints, cache, recovery, artifact validation |
| **[Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)** | Python / Automation | multi-source vacancy parsing, adapters, fault isolation, deduplication, Excel export |
| **[ZeTer Video Downloader](https://github.com/zeter1/ZeTer-Video-Downloader)** | Python / Multimedia | yt-dlp, MP4/MP3, format selection, remux/transcoding fallback, ffprobe validation, tests |
| **[ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter)** | Python / Windows · Multimedia | Tkinter, FFmpeg/FFprobe, video-to-MP3 and up-to-10-hour MP4 merging, MP3 backup, diagnostics, regression tests, Windows EXE CI |
| **[Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)** | Python / Windows | Microsoft SAPI/COM, Windows TTS, MP3, global hotkeys, state persistence, long-job recovery |
| **[Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)** | Python / Windows | WinAPI, WTS API, mutex, power management, self-test, bounded logging |
| **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** | Hybrid Desktop/Web | Python + JavaScript, pywebview bridge, modular frontend, local-first state, backup/recovery |
| **[Zeter Video Editor](https://github.com/zeter1/zeter-video-editor)** | Desktop / Video | Tauri, React, TypeScript, Rust, FFmpeg; multi-track editing and local projects; release-readiness work, no public GitHub release yet |

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

<details>
<summary>Explore code, tests, and CI links</summary>

A technical reviewer can jump directly from the profile to code and checks:

- **ZeTer Photo Editor:** [`src/adapters/`](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters) · [`tests/color-management.test.mjs`](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs) · [CI](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/.github/workflows/ci.yml).
- **ZAP ZONE:** [`src/core/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/core) · [`src/combat/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/combat) · [`src/weapons/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/weapons) · [structural validation](https://github.com/zeter1/ZAP-ZONE/blob/main/scripts/validate-structure.mjs) · [browser smoke CI](https://github.com/zeter1/ZAP-ZONE/blob/main/.github/workflows/validate.yml).
- **BizPilot:** [`js/cashflow.js`](https://github.com/zeter1/BizPilot/blob/main/js/cashflow.js) · [`scripts/test-cashflow.mjs`](https://github.com/zeter1/BizPilot/blob/main/scripts/test-cashflow.mjs) · [`scripts/browser-smoke.sh`](https://github.com/zeter1/BizPilot/blob/main/scripts/browser-smoke.sh) · [CI](https://github.com/zeter1/BizPilot/blob/main/.github/workflows/validate.yml).
- **CYBER RACE:** [`src/ai/opponent-brain.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/ai/opponent-brain.js) · [`src/weapons/ballistics.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/weapons/ballistics.js) · [`src/core/seeded-rng.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/core/seeded-rng.js) · [`tests/scenarios.mjs`](https://github.com/zeter1/CYBER-RACE/blob/main/tests/scenarios.mjs) · [CI](https://github.com/zeter1/CYBER-RACE/blob/main/.github/workflows/validate.yml).
- **Forest Hunter:** [`src/ai/boar-brain.js`](https://github.com/zeter1/ForestHunter/blob/main/src/ai/boar-brain.js) · [`src/weapons/combat-rules.js`](https://github.com/zeter1/ForestHunter/blob/main/src/weapons/combat-rules.js) · [`src/core/seeded-rng.js`](https://github.com/zeter1/ForestHunter/blob/main/src/core/seeded-rng.js) · [`tests/scenarios.mjs`](https://github.com/zeter1/ForestHunter/blob/main/tests/scenarios.mjs) · [CI](https://github.com/zeter1/ForestHunter/blob/main/.github/workflows/validate.yml).
- **Screen Recorder Pro:** [`screen_recorder/`](https://github.com/zeter1/Screen-Recorder-Pro/tree/main/screen_recorder) · [capture recovery](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_capture_recovery.py) · [save safety](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_save_safety.py).
- **ZeTer Media Converter:** [audio pipeline](https://github.com/zeter1/ZeTer-Media-Converter/blob/main/videovaudio/audio/folder_workflow.py) · [video pipeline](https://github.com/zeter1/ZeTer-Media-Converter/blob/main/videovaudio/video/folder_workflow.py) · [regressions](https://github.com/zeter1/ZeTer-Media-Converter/blob/main/tools/test_audio_regressions.py) · [EXE CI](https://github.com/zeter1/ZeTer-Media-Converter/blob/main/.github/workflows/build-windows.yml) · [EXE v3.3.5](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5).
- **BSOD Investigator:** [`bsod_investigator.py`](https://github.com/zeter1/BSOD-Investigator/blob/main/bsod_investigator.py) · [`docs/`](https://github.com/zeter1/BSOD-Investigator/tree/main/docs).
- **VoiceFlow:** [`voiceflow.py`](https://github.com/zeter1/VoiceFlow/blob/main/voiceflow.py) · [`docs/`](https://github.com/zeter1/VoiceFlow/tree/main/docs).

</details>

## Technologies

<details>
<summary>Explore the full technology stack</summary>

**Web:** `HTML` · `CSS` · `JavaScript` · `Canvas 2D` · `WebGL` · `Three.js` · `Web Audio API` · `IndexedDB` · `localStorage`

**Python / Windows:** `Python` · `Tkinter` · `WinAPI` · `ctypes` · `COM / SAPI` · `pywebview` · `PyInstaller`

**AI / Multimedia:** `FFmpeg` · `FFprobe` · `yt-dlp` · `Whisper` · `faster-whisper` · `CUDA` · `Edge TTS`

**Data / Automation:** `SQLite` · `JSON` · `pandas` · `openpyxl` · `requests` · `BeautifulSoup`

**Engineering:** `Git` · `GitHub Actions` · regression tests · smoke tests · diagnostics · backup/recovery

</details>

## Navigation

- **[USER_GUIDE_EN.md](USER_GUIDE_EN.md)** — choose a program, download, and get started.
- **[PROJECTS_EN.md](PROJECTS_EN.md)** — project map.
- **[REVIEW_GUIDE_EN.md](REVIEW_GUIDE_EN.md)** — 5/15/30-minute technical review path.
- **[ENGINEERING_EN.md](ENGINEERING_EN.md)** — engineering principles and examples.
- **[SUPPORT_EN.md](SUPPORT_EN.md)** — diagnostics and bug-report guidance for Web, Python, and hybrid projects.

## Contacts

- **Email:** zeter11@gmail.com
- **Telegram:** https://t.me/zeter1
- **LinkedIn:** https://www.linkedin.com/in/zeter/
- **Facebook:** https://www.facebook.com/zeter1
- [https://vk.ru/zeter1](https://vk.ru/zeter1)
- [https://www.instagram.com/zeter1992/](https://www.instagram.com/zeter1992/)
- [https://tenchat.ru/zeter](https://tenchat.ru/zeter)
- [https://x.com/zeter1](https://x.com/zeter1)
- [https://www.threads.com/@zeter1992](https://www.threads.com/@zeter1992)
- [https://ok.ru/zeter1](https://ok.ru/zeter1)
- [https://t.me/zeterchat](https://t.me/zeterchat) — Telegram group: about me, projects and chat
- **Website / portfolio:** https://dkl.do.am/
