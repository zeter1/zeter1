**Язык / Language:** [Русский](ENGINEERING.md) · **English**

# Engineering approach

This document complements the profile and describes practices used across the published projects. They are applied where they fit the problem rather than as mandatory ceremony.

## 1. Diagnostics should help find the root cause

A large raw log is often not enough: the important event gets lost among repetitions. In complex projects, diagnostics are separated by responsibility and preserve error context, operation parameters, traceback, key events, and a final summary.

Examples:

- **BSOD Investigator** combines crash dump data, WinDbg/CDB output, Event Log records, driver information, and history from previous failures.
- **Screen Recorder Pro** separates FFmpeg command diagnostics, timing, recording smoothness, audio devices, and process lifecycle.
- **Vacancy Parser Pro** creates a diagnostic session for each search and separates problems by source.
- **Windows PC Locker** limits log size and keeps compact context about the latest important problem.

## 2. A long-running operation should not be a black box

For operations that may run for minutes or hours, it is important to know the current stage, cancel safely, and preserve completed work where possible.

Approaches used include:

- checkpoints and recovery;
- heartbeat for long external processes;
- bounded retries instead of infinite loops;
- timeouts;
- return-code validation;
- reuse of already-created intermediate artifacts;
- safe cleanup of temporary data.

A representative example is **Video Translator Pro**, where one user operation includes speech recognition, translation, TTS, and several FFmpeg stages.

## 3. A successful command does not necessarily mean a successful result

Whenever possible, the final artifact is validated.

Examples:

- final video output is inspected through FFprobe;
- the downloader distinguishes download, remux, and transcoding and validates the produced media file;
- diagnostic analysis separates the presence of a signal from confidence in the conclusion;
- self-tests exercise critical scenarios without performing potentially destructive actions.

## 4. External dependencies need failure boundaries

A website, API, driver, FFmpeg, TTS service, or hardware device can fail independently of the application.

For that reason, the projects use:

- adapter isolation;
- local error handling;
- fallback only where it is safe;
- bounded retries;
- explicit child-process termination;
- diagnostic context for the specific external dependency.

**Vacancy Parser Pro** demonstrates this across several vacancy sites; **Video Translator Pro** applies the same principle to TTS, translation, and FFmpeg.

## 5. User data should not be mixed with source code

Runtime data, settings, caches, history, and diagnostics are kept out of Git. Projects where user data matters also design explicit backup and recovery flows.

**ZeTer OS** uses a local-first model, exports, backups, and restore points. Other desktop projects store local settings and runtime data separately from the repository.

## 6. A very large file is a signal to inspect responsibility boundaries

As a project grows, code is split into modules when doing so reduces coupling and makes navigation easier.

Examples:

- **Screen Recorder Pro** separates UI, recording, audio, FFmpeg commands, process management, screenshots, and diagnostics across focused components and mixins.
- **ZeTer OS** uses a modular JavaScript frontend with a separate Python/native bridge.
- **Universal Video Downloader** includes a code map and tools for finding the smallest scope required for a change.

## 7. Verification should match real risk

Not every function can be fully tested in CI. Microphones, GPUs, Desktop Duplication, system audio, and real interactive Windows sessions require physical runtime conditions.

The projects therefore combine:

- `py_compile` / `compileall`;
- unit and regression tests;
- self-tests;
- smoke tests;
- structural checks;
- GitHub Actions;
- manual verification for hardware-dependent scenarios.

The goal is not to create the illusion of 100% coverage, but to automate the parts that can be verified reliably.

## 8. AI-assisted development requires the same verification as regular development

ChatGPT and Codex are used to accelerate analysis, refactoring, debugging, and implementation. A generated change is not treated as correct simply because the code looks plausible.

Larger projects use architecture documentation, code maps, `AGENTS.md`, automated checks, and diagnostics. This helps reduce change scope and lowers regression risk.

## Repositories

- [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)
- [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)
- [VoiceFlow](https://github.com/zeter1/VoiceFlow)
- [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)
- [ZeTer OS](https://github.com/zeter1/ZeTer-OS)
- [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)
- [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)
- [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)
- [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)
