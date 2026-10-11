**Язык / Language:** [Русский](REVIEW_GUIDE.md) · **English**

[Profile](README_EN.md) · [Applications](USER_GUIDE_EN.md) · **Technical review** · [Support](SUPPORT_EN.md)

# Technical portfolio review guide

This page provides a short route through the two main tracks of the profile: **Web Development** and **Python Development**. The goal is to move quickly from a description to code, architecture, tests, and verifiable engineering decisions.

## 5-minute review

Choose **one route relevant to the role**. Start with one project and compare a concrete implementation with its checks.

| Area | Code → checks | What to inspect |
|---|---|---|
| Web / business applications — **BizPilot** | [`js/cashflow.js`](https://github.com/zeter1/BizPilot/blob/main/js/cashflow.js) → [`scripts/test-cashflow.mjs`](https://github.com/zeter1/BizPilot/blob/main/scripts/test-cashflow.mjs) | How financial calculations are separated from the UI, and which edge cases are checked. |
| Python / Windows — **Screen Recorder Pro** | [`screen_recorder/`](https://github.com/zeter1/Screen-Recorder-Pro/tree/main/screen_recorder) → [`verify_capture_recovery.py`](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_capture_recovery.py) · [`verify_save_safety.py`](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_save_safety.py) | Capture recovery and output saving, and the scenarios covered by the checks. |
| Web / graphics — **ZeTer Photo Editor** | [`src/adapters/`](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters) → [`tests/color-management.test.mjs`](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs) | The boundary between file formats and internal image data; color-management checks. |

In five minutes: **1)** read the project description; **2)** open its code and corresponding checks from the table; **3)** inspect what the workflow in `.github/workflows/` runs, and the relevant result under **Actions**. Match the branch and commit: a green run for another revision does not verify the current one.

This route identifies a topic for discussion. It does not replace a detailed review or manual application testing. For games, local AI, and system diagnostics, use the map below.

## Engineering evidence map

| What to evaluate | Project | Where to look | What it demonstrates |
|---|---|---|---|
| Browser image architecture | ZeTer Photo Editor | [`src/adapters/`](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters), [`tests/color-management.test.mjs`](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs), [CI](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/.github/workflows/ci.yml) | layered document model, PSD/PSB, typed pixel buffers, ICC/CMYK tests |
| WebGL/game architecture | ZAP ZONE | [`src/core/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/core), [`src/combat/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/combat), [`src/weapons/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/weapons), [validation](https://github.com/zeter1/ZAP-ZONE/blob/main/scripts/validate-structure.mjs), [CI](https://github.com/zeter1/ZAP-ZONE/blob/main/.github/workflows/validate.yml) | modular JavaScript, real-time loop, tactical AI, browser boot smoke test |
| Local-first web + runtime recovery | BizPilot | [`js/cashflow.js`](https://github.com/zeter1/BizPilot/blob/main/js/cashflow.js), [`scripts/test-cashflow.mjs`](https://github.com/zeter1/BizPilot/blob/main/scripts/test-cashflow.mjs), [`scripts/browser-smoke.sh`](https://github.com/zeter1/BizPilot/blob/main/scripts/browser-smoke.sh), [CI](https://github.com/zeter1/BizPilot/blob/main/.github/workflows/validate.yml) | state lifecycle, cash-flow contract, regression tests, and real browser startup proof |
| Deterministic gameplay simulation | CYBER RACE | [`src/ai/opponent-brain.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/ai/opponent-brain.js), [`src/weapons/ballistics.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/weapons/ballistics.js), [`tests/scenarios.mjs`](https://github.com/zeter1/CYBER-RACE/blob/main/tests/scenarios.mjs), [`cyber-replay.json`](https://github.com/zeter1/CYBER-RACE/blob/main/tests/fixtures/cyber-replay.json), [CI](https://github.com/zeter1/CYBER-RACE/blob/main/.github/workflows/validate.yml) | seeded AI/attack/rocket replay plus a headless WebGL integration gate |
| Deterministic gameplay simulation | Forest Hunter | [`src/ai/boar-brain.js`](https://github.com/zeter1/ForestHunter/blob/main/src/ai/boar-brain.js), [`src/weapons/combat-rules.js`](https://github.com/zeter1/ForestHunter/blob/main/src/weapons/combat-rules.js), [`tests/scenarios.mjs`](https://github.com/zeter1/ForestHunter/blob/main/tests/scenarios.mjs), [`forest-replay.json`](https://github.com/zeter1/ForestHunter/blob/main/tests/fixtures/forest-replay.json), [CI](https://github.com/zeter1/ForestHunter/blob/main/.github/workflows/validate.yml) | seeded boar/combat/reload/deployable replay plus a headless WebGL integration gate |
| Multimedia recovery | Screen Recorder Pro | `screen_recorder/`, `verify_capture_recovery.py`, `verify_save_safety.py` | FFmpeg lifecycle, recovery, output safety |
| Windows diagnostics | BSOD Investigator | `bsod_investigator.py`, `docs/`, `--self-test` | crash-evidence processing and reproducible self-check |
| Local speech-to-text | VoiceFlow | `voiceflow.py`, `docs/` | faster-whisper, CPU/CUDA, Windows input |
| Long AI/multimedia workflow | Video Translator Pro | `videotranslator/`, `tests/`, `tools/`, `AGENTS.md` | checkpoints, recovery, staged processing |
| Hybrid desktop/web | ZeTer OS | `app/`, `tools/check_project.py` | Python/native bridge + modular JavaScript frontend |
| Downloader/media pipeline | Universal Video Downloader | `src/`, `tests/`, `problem_log_validator.py` | format strategy, validation, and diagnostics |

## 15-minute review

### 1. Compare Web architectures

- **ZeTer Photo Editor** — a large browser application with rendering, format adapters, masks, typed pixel data, and persistence.
- **ZAP ZONE** — a real-time Three.js application with separated runtime/gameplay modules.
- **BizPilot** — a local-first business application with a testable cash-flow engine, regression suite, and diagnosable headless browser boot.
- **CYBER RACE / Forest Hunter** — beyond modularization, seeded replay fixtures exercise deterministic AI/combat frame sequences while headless WebGL boot remains the final integration gate.

### 2. Compare Python architectures

- `Screen-Recorder-Pro/screen_recorder/` — modular Windows multimedia application;
- `Universal-Video-Downloader/src/` — downloader with separate tests/scripts/docs;
- `Video-Translator-Pro/videotranslator/` — package structure for a long-running pipeline;
- `ZeTer-OS/app/` — hybrid Python + JavaScript boundary;
- `Vacancy-Parser-Pro` — scraper / GUI / logging responsibilities.

### 3. Review the verification strategy

Compare evidence levels:
1. **syntax/compile**;
2. **unit/regression**;
3. **integration/self-test**;
4. **browser smoke/runtime**;
5. **manual Windows / GPU / audio verification**.

The key rule: a claim should match the level of verification that was actually performed.

## 30-minute review

### A. Web graphics — ZeTer Photo Editor

Inspect:
- document model, layers/groups/masks;
- render state vs editable source separation;
- PSD/PSB import/export;
- 16/32-bit typed buffers;
- ICC/CMYK path;
- crash autosave;
- regression tests and CI.

### B. WebGL / AI — ZAP ZONE

Inspect:
- engine / weapons / combat / entities / progression / runtime boundaries;
- tactical AI;
- ballistics and weapon handling;
- browser boot smoke test;
- performance/recovery contracts.

### C. Windows multimedia — Screen Recorder Pro

Inspect:
- FFmpeg command construction;
- capture/encoding selection;
- child-process lifecycle;
- capture recovery;
- save safety;
- what GitHub Actions actually execute.

### D. System diagnostics — BSOD Investigator

Inspect:
- how dump/Event Log/driver data become an evidence model;
- how strong and weak signals are separated;
- history across independent crashes;
- safe self-test.

### E. Local AI — VoiceFlow

Inspect:
- audio → faster-whisper pipeline;
- CPU/CUDA paths;
- stable-fragment insertion;
- Windows input fallbacks;
- the boundary between CI-verifiable and hardware/runtime-dependent behavior.

## Strong signals to look for

**Web:** state lifecycle, rendering budgets, module boundaries, graceful degradation, persistence, browser smoke tests.

**Python:** process lifecycle, WinAPI integration, recovery, external-tool validation, structured diagnostics.

**Across both:** tests, CI, documentation, constrained change scope, and honest labeling of what is not yet verified.

## More navigation

- [Main profile](README_EN.md)
- [Project map](PROJECTS_EN.md)
- [Engineering approach](ENGINEERING_EN.md)
- [Support and diagnostics](SUPPORT_EN.md)
