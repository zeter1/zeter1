# Dmitry Kolesnichenko

**Python Developer · Windows Applications · Automation · AI-assisted Development**

I build practical Python software for Windows, automation, system diagnostics, file processing, and multimedia workflows. My focus is not only on implementing features, but also on reliability, useful diagnostics, safe data handling, and maintainable code.

## What I work with

- **Python:** desktop applications, automation, background tasks, file and process management
- **Windows:** system integration, global hotkeys, autostart, processes, diagnostics, Windows API
- **Data:** JSON, SQLite, pandas, openpyxl
- **Networking & parsing:** requests, BeautifulSoup
- **Multimedia:** FFmpeg, FFprobe, yt-dlp
- **System monitoring:** psutil
- **UI:** Tkinter, pywebview, HTML, CSS, JavaScript
- **Development:** Git, PyInstaller, debugging, logging, refactoring, testing
- **AI-assisted engineering:** ChatGPT and Codex for code analysis, implementation, debugging, review, and documentation — with manual verification of changes

## Engineering focus

I pay particular attention to:

- root-cause debugging instead of masking symptoms;
- structured logs that make failures easier to reproduce and analyze;
- timeouts, bounded retries, temporary files, and correct process cleanup;
- preserving user data with backups, recovery, and safe persistence;
- keeping long-running operations responsive and resilient to individual failures;
- refactoring large modules without breaking existing behavior;
- reviewing Git diffs and validating AI-generated changes before accepting them.

## Featured projects

### [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)

Windows diagnostic application for investigating BSODs and system crashes. It works with crash dumps, Windows Event Log data, driver/process context, SQLite history, diagnostic reports, and automated self-checks.

The repository includes documented setup and build steps, runtime-artifact protection through `.gitignore`, and GitHub Actions checks for Python syntax and the built-in self-test.

### [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)

Modular Windows screen-recording application built with Python and FFmpeg. It includes global hotkeys, system-audio and microphone handling, multi-monitor capture, webcam/annotation components, recording-session management, recovery-oriented diagnostics, and project verification scripts.

The project is split into dedicated components and mixins instead of a single monolithic file, and includes automated structural checks through GitHub Actions.

### [VoiceFlow](https://github.com/zeter1/VoiceFlow)

Offline Windows voice-dictation application built with Python and faster-whisper. It records microphone input, transcribes speech locally and inserts confirmed realtime text chunks directly into the currently focused field, allowing the user to switch between Telegram, browsers, documents, editors and other applications during one recording session.

The project includes configurable global hotkeys, CPU/CUDA model execution, voice commands, pause-aware punctuation, optional local text cleanup and LanguageTool grammar processing, system-tray/background operation, Windows autostart, movable recording notifications and detailed diagnostic logs for hotkeys, recording state, streaming, text insertion, notifications and GPU problems.

### [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)

Windows desktop video translation and dubbing application built with Python, Whisper, Edge TTS, gTTS and FFmpeg. It recognizes speech, translates it, generates a new voice track and can preserve the full translated phrase with Pause Sync instead of forcing aggressive x2–x4 speech compression.

The project includes translation checkpoints, resumable batch processing, persistent TTS recovery cache, bounded network retries, Edge/gTTS fallback handling, final MP4 validation, FFmpeg-based assembly, structured diagnostic sessions and compact Codex-oriented issue summaries for long-running failures.

### [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)

Windows desktop text-to-speech and MP3 conversion application built with Python, Tkinter, Microsoft SAPI and FFmpeg. It supports multiple persistent text tabs, per-tab global hotkeys for capturing selected text from other applications, playback-device selection, extended speed and pitch controls, pause/resume bookmarks, optional deletion of read sentences, and long-text MP3 generation.

The project includes resumable conversion checkpoints, safe text backups, atomic settings/workspace persistence, MP3 output validation, bounded SAPI retries, disk-space forecasting, and structured diagnostic logs designed for troubleshooting with ChatGPT/Codex.

### [ZeTer OS](https://github.com/zeter1/ZeTer-OS)

Hybrid Windows productivity application built with Python, pywebview, HTML, CSS and modular JavaScript. It combines multiple workspaces, notes, tasks, calendar data, files, tables and local-first persistence with backups, restore points and portable release tooling.

The repository includes architecture and data-model documentation, repository-specific `AGENTS.md`, structural validation, JavaScript scenario smoke tests, native bridge checks and release-builder verification.

### [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)

Windows desktop vacancy aggregator built with Python and Tkinter. It searches Rabota.by, HH.ru, Praca.by, Belmeta and GSZ.gov.by, applies local salary and vacancy filters, removes duplicates, opens source vacancies directly and exports results to Excel.

The project includes resilient per-source fallback logic, structured diagnostic sessions for parser and network failures, network-free regression tests, GitHub Actions verification and Windows EXE build tooling.

## Other project areas

I have built more than 20 personal software projects, primarily Python applications and Windows utilities. They include:

- file, archive, and long-path automation tools;
- text-to-speech and transcription utilities;
- network traffic and process monitoring.

More selected projects will be published here as separate, documented repositories.

## Currently looking for

I am interested in **Junior Python Developer**, **Python Automation Developer**, internship, and project-based opportunities where I can work on real applications, automation, Windows tooling, and existing Python codebases.

## Contact

- Email: **zeter11@gmail.com**
- Telegram: **https://t.me/zeter1**
