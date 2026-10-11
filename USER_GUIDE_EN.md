**Язык / Language:** [Русский](USER_GUIDE.md) · **English**

# Choose, download, and get started

Choose your task below. Project names link to source and README instructions; **Builds** links lead to published Windows files. For a technical assessment, use the separate [code and verification review route](REVIEW_GUIDE_EN.md).

## Browser applications and games

| Project | Purpose | Getting started |
|---|---|---|
| [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) | Image editing, layers, selections, drawing, and effects | [Instructions](https://github.com/zeter1/ZeTer-Photo-Editor#запуск-на-windows): download the source ZIP, extract it, open `start.bat` or `index.html`. Ordinary use does not require Python or Node.js. |
| [BizPilot](https://github.com/zeter1/BizPilot) | Small-business clients, tasks, deals, income, and expenses | [Instructions](https://github.com/zeter1/BizPilot#запуск): download the source ZIP, extract it, open `index.html` in a modern browser. |
| [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE) | Browser 3D shooter with bots | [Startup and controls](https://github.com/zeter1/ZAP-ZONE#readme). Requires a modern desktop browser with WebGL; see its README for resource-loading requirements. |
| [CYBER RACE](https://github.com/zeter1/CYBER-RACE) | Armed-car racing game | [Startup and controls](https://github.com/zeter1/CYBER-RACE#запуск). A local HTTP server is recommended; the command is documented in its README. |
| [Forest Hunter](https://github.com/zeter1/ForestHunter) | 3D hunting and survival game | [Startup and controls](https://github.com/zeter1/ForestHunter#запуск). A local HTTP server is recommended; the command is documented in its README. |

**Download a source ZIP:** open the repository → green **Code** button → **Download ZIP** → extract the entire folder. The image editor and BizPilot do not require an npm build for ordinary use. Game WebGL and network-library requirements are documented in their own READMEs.

BizPilot stores its workspace in the browser. Export a ZIP backup from its data section before clearing browser storage or changing browsers. Save image-editor projects to files; emergency autosave does not replace your own copy.

## Windows applications

All published builds below are currently marked **Pre-release**, for exploration and testing. Each application's README owns its prerequisites and known limitations.

| Task | Application and instructions | Download |
|---|---|---|
| Record the screen and audio, take screenshots | [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro#readme) | [Builds](https://github.com/zeter1/Screen-Recorder-Pro/releases) |
| Dictate text into Windows applications | [VoiceFlow](https://github.com/zeter1/VoiceFlow#readme) | [Builds](https://github.com/zeter1/VoiceFlow/releases) |
| Translate and voice over videos | [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro#readme) | [Builds](https://github.com/zeter1/Video-Translator-Pro/releases) |
| Download videos or extract MP3 audio | [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader#readme) | [Builds](https://github.com/zeter1/Universal-Video-Downloader/releases) |
| Convert text to speech and MP3 | [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows#readme) | [Builds](https://github.com/zeter1/Text-to-MP3-Windows/releases) |
| Find vacancies, deduplicate, and export to Excel | [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro#readme) | [Builds](https://github.com/zeter1/Vacancy-Parser-Pro/releases) |
| Investigate Windows blue-screen causes | [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator#readme) | [Builds](https://github.com/zeter1/BSOD-Investigator/releases) |
| Lock a Windows session and control sleep prevention | [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker#readme) | [Builds](https://github.com/zeter1/Windows-PC-Locker/releases) |
| Organize notes, tasks, and a local workspace | [ZeTer OS](https://github.com/zeter1/ZeTer-OS#readme) | [Builds](https://github.com/zeter1/ZeTer-OS/releases) |

### Downloading a ready-made application

1. Follow its **Builds** link and read the release notes.
2. Under **Assets**, select the application `.exe` or Windows-build `.zip`. **Source code** is not a ready-made application.
3. Extract the entire archive and keep accompanying files beside the executable. Follow the application's README.
4. If a SHA-256 checksum file is published, use it to verify download integrity.

A ready-made build may differ from the current source revision. FFmpeg, speech models, Windows voices, GPU drivers, and external-service requirements depend on the application. An `.exe` alone does not establish that every component is bundled. Source startup is documented separately in each project's README.

## Video editor under development

[Zeter Video Editor](https://github.com/zeter1/zeter-video-editor) is a Windows video editor built with Tauri, React, TypeScript, Rust, and FFmpeg, with multi-track editing and local projects. There is no ready-made public build in GitHub Releases yet. Start with its [README](https://github.com/zeter1/zeter-video-editor#readme) and [current status](https://github.com/zeter1/zeter-video-editor/blob/main/PROJECT_STATUS.md); developer instructions describe source startup.

## Reporting a problem

Open **Issues** in the relevant project. Include the version, Windows or browser details, steps, expected result, and actual result. Provide a small example without personal files or secrets; see the [bug-report guide](SUPPORT_EN.md).

Contact:

- [https://t.me/zeter1](https://t.me/zeter1)
- [zeter11@gmail.com](mailto:zeter11@gmail.com)
- [https://www.facebook.com/zeter1](https://www.facebook.com/zeter1)
- [https://vk.ru/zeter1](https://vk.ru/zeter1)
- [https://www.instagram.com/zeter1992/](https://www.instagram.com/zeter1992/)
- [https://tenchat.ru/zeter](https://tenchat.ru/zeter)
- [https://x.com/zeter1](https://x.com/zeter1)
- [https://www.threads.com/@zeter1992](https://www.threads.com/@zeter1992)
- [https://ok.ru/zeter1](https://ok.ru/zeter1)
- [https://t.me/zeterchat](https://t.me/zeterchat) — Telegram group: about me, projects and chat

Technical detail: [project map](PROJECTS_EN.md) · [engineering approach](ENGINEERING_EN.md).
