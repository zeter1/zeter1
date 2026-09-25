**Язык / Language:** [Русский](ENGINEERING.md) · **English**

# Engineering approach

This document complements the profile and describes practices used across my **Python** and **Web** projects. The goal is not to apply the same template everywhere, but to use verifiable engineering choices that match the real risk of each project.

## 1. Diagnostics should help find the root cause

Complex projects preserve the operation stage, inputs, traceback or error code, external-component state, and a useful summary instead of relying on one large raw log.

Examples:
- **BSOD Investigator** combines crash dumps, WinDbg/CDB, Event Log data, driver metadata, and failure history.
- **Screen Recorder Pro** separates FFmpeg commands, timing, audio devices, capture smoothness, and process lifecycle.
- **Vacancy Parser Pro** isolates problems by external source.
- Browser projects keep runtime/rendering failures visible across UI, game loops, and Web APIs.

## 2. Long-running operations should not be black boxes

Approaches include checkpoints, recovery, heartbeats, bounded retries, timeouts, return-code validation, reuse of intermediate artifacts, and safe cleanup.

**Video Translator Pro** demonstrates this in a long Whisper → translation → TTS → FFmpeg pipeline.

## 3. A successful command does not necessarily mean a successful result

Whenever possible, the final artifact or observable behavior is validated:
- video through FFprobe;
- download/remux/transcoding output through media validation;
- browser runtime through actual initialization to an explicit ready marker, not merely HTTP availability;
- graphics formats through regression tests around import/export contracts;
- critical scenarios through safe self-tests.

A concrete example is **BizPilot**: syntax and local-asset checks passed, but the first real headless Chrome smoke stopped on `cashflowForecast is not defined`. The failure was treated as a real runtime regression rather than a CI problem; the cash-flow logic was then moved into a testable module, regression tests and boot-stage diagnostics were added, and the browser smoke became green.

## 4. External dependencies need failure boundaries

An API, website, driver, FFmpeg, CDN, WebGL context, or audio device can fail independently of the application.

Projects therefore use:
- integration isolation;
- local error handling;
- fallback only where correct;
- bounded retry;
- explicit child-process termination;
- diagnostic context for the failing dependency.

Web projects add CDN fallback, WebGL context recovery, and graceful quality degradation where appropriate.

## 5. Browser application state is part of architecture

A local-first application should explicitly define:
- what lives in `localStorage`, IndexedDB, or memory;
- what counts as user data;
- how backup/restore works;
- how crash/reload recovery works;
- what can be safely discarded;
- what must never enter Git.

**BizPilot** uses local state with ZIP backup/restore. **ZeTer Photo Editor** uses IndexedDB for crash recovery of unsaved documents.

## 6. Rendering and real-time code need budgets

In Canvas/WebGL projects, correctness is not enough; frame budget, memory, and real-time object count also matter.

Approaches include:
- `requestAnimationFrame`;
- object pools;
- `InstancedMesh`;
- spatial grids;
- bounded heavy operations;
- bounded caches;
- adaptive quality;
- typed pixel pipelines where Canvas8 is not sufficient.

This is visible in **ZeTer Photo Editor**, **ZAP ZONE**, **CYBER RACE**, and **Forest Hunter**.

## 7. Large files are a signal to inspect responsibility boundaries

As projects grow, code is split when doing so reduces coupling and makes future changes easier.

Examples:
- **Screen Recorder Pro** separates UI, capture, audio, FFmpeg, process management, and diagnostics.
- **ZeTer OS** uses a modular JavaScript frontend with a separate Python/native bridge.
- **ZAP ZONE** separates engine, weapons, player state, combat, entities, progression, and runtime.
- **CYBER RACE** and **Forest Hunter** now go beyond decomposition: AI/combat state evolution is exposed as dependency-injected simulation, and versioned seeded fixtures replay frame sequences deterministically. Structural validators prevent simulation logic from silently collapsing back into runtime.
- **BizPilot** separates its cash-flow engine from UI orchestration so financial logic can be regression-tested independently of the DOM.
- **Universal Video Downloader** includes a code map and tools for finding the smallest change scope.

## 8. Verification should match real risk

The projects combine:
- syntax / compile checks;
- unit and regression tests;
- self-tests;
- structural checks;
- deterministic gameplay contract tests without a browser;
- seeded replay/regression scenarios for AI/combat state-transition sequences;
- structural architecture checks;
- headless WebGL browser boot smoke with an explicit ready marker;
- GitHub Actions;
- manual runtime verification where a real Windows session, GPU, audio device, or interactive browser is required.

A green CI run is not treated as proof that a hardware-dependent feature has been fully verified.

## 9. User data needs its own strategy

Settings, runtime state, caches, crash recovery, diagnostic artifacts, and user documents should not accidentally mix with source code.

Depending on the project, the design uses:
- local storage outside the repository;
- backup/restore;
- crash autosave;
- bounded logs/caches;
- diagnostic-data sanitization;
- explicit `.gitignore` rules.

## 10. AI-assisted development requires the same verification as regular development

ChatGPT and Codex are used for analysis, refactoring, debugging, and implementation. A change is not considered correct just because it looks plausible.

Large projects use architecture docs, code maps, `AGENTS.md`, tests, CI, and diagnostics to reduce change scope and regression risk.

## Repositories by area

**Web:** [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) · [BizPilot](https://github.com/zeter1/BizPilot) · [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE) · [CYBER RACE](https://github.com/zeter1/CYBER-RACE) · [Forest Hunter](https://github.com/zeter1/ForestHunter)

**Python / Windows:** [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) · [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator) · [VoiceFlow](https://github.com/zeter1/VoiceFlow) · [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro) · [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro) · [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader) · [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows) · [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)

**Hybrid:** [ZeTer OS](https://github.com/zeter1/ZeTer-OS)
