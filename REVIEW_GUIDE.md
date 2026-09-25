**Язык / Language:** **Русский** · [English](REVIEW_GUIDE_EN.md)

# Гайд по техническому просмотру портфолио

Этот файл даёт короткий маршрут по двум основным направлениям профиля: **Web Development** и **Python Development**. Цель — быстро перейти от описания к коду, архитектуре, тестам и проверяемым инженерным решениям.

## 5 минут

Если времени мало, открыть пять проектов:

1. **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** — browser graphics, Canvas, PSD/PSB, high-depth pixel pipeline, masks и color management.
2. **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** — Three.js/WebGL, modular JavaScript, tactical AI, combat systems, browser smoke test.
3. **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** — Python/Windows, FFmpeg, capture lifecycle, recovery и verification scripts.
4. **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** — системная диагностика, crash dumps, WinDbg/CDB и evidence-based analysis.
5. **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** — local AI, faster-whisper, CPU/CUDA и Windows input.

Этого достаточно, чтобы увидеть обе стороны портфолио: сложный browser runtime и глубокую Python/Windows-интеграцию.

## Карта инженерных доказательств

| Что проверить | Проект | Куда смотреть | Что показывает |
|---|---|---|---|
| Browser image architecture | ZeTer Photo Editor | [`src/adapters/`](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters), [`tests/color-management.test.mjs`](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs), [CI](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/.github/workflows/ci.yml) | layered document model, PSD/PSB, typed pixel buffers, ICC/CMYK tests |
| WebGL/game architecture | ZAP ZONE | [`src/core/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/core), [`src/combat/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/combat), [`src/weapons/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/weapons), [validation](https://github.com/zeter1/ZAP-ZONE/blob/main/scripts/validate-structure.mjs), [CI](https://github.com/zeter1/ZAP-ZONE/blob/main/.github/workflows/validate.yml) | modular JavaScript, realtime loop, tactical AI, browser boot smoke test |
| Local-first web + runtime recovery | BizPilot | [`js/cashflow.js`](https://github.com/zeter1/BizPilot/blob/main/js/cashflow.js), [`scripts/test-cashflow.mjs`](https://github.com/zeter1/BizPilot/blob/main/scripts/test-cashflow.mjs), [`scripts/browser-smoke.sh`](https://github.com/zeter1/BizPilot/blob/main/scripts/browser-smoke.sh), [CI](https://github.com/zeter1/BizPilot/blob/main/.github/workflows/validate.yml) | state lifecycle, cash-flow contract, regression tests и реальный browser startup proof |
| Deterministic gameplay simulation | CYBER RACE | [`src/ai/opponent-brain.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/ai/opponent-brain.js), [`src/weapons/ballistics.js`](https://github.com/zeter1/CYBER-RACE/blob/main/src/weapons/ballistics.js), [`tests/scenarios.mjs`](https://github.com/zeter1/CYBER-RACE/blob/main/tests/scenarios.mjs), [`cyber-replay.json`](https://github.com/zeter1/CYBER-RACE/blob/main/tests/fixtures/cyber-replay.json), [CI](https://github.com/zeter1/CYBER-RACE/blob/main/.github/workflows/validate.yml) | seeded AI/attack/rocket replay + headless WebGL integration gate |
| Deterministic gameplay simulation | Forest Hunter | [`src/ai/boar-brain.js`](https://github.com/zeter1/ForestHunter/blob/main/src/ai/boar-brain.js), [`src/weapons/combat-rules.js`](https://github.com/zeter1/ForestHunter/blob/main/src/weapons/combat-rules.js), [`tests/scenarios.mjs`](https://github.com/zeter1/ForestHunter/blob/main/tests/scenarios.mjs), [`forest-replay.json`](https://github.com/zeter1/ForestHunter/blob/main/tests/fixtures/forest-replay.json), [CI](https://github.com/zeter1/ForestHunter/blob/main/.github/workflows/validate.yml) | seeded boar/combat/reload/deployable replay + headless WebGL integration gate |
| Multimedia recovery | Screen Recorder Pro | `screen_recorder/`, `verify_capture_recovery.py`, `verify_save_safety.py` | FFmpeg lifecycle, recovery, output safety |
| Windows diagnostics | BSOD Investigator | `bsod_investigator.py`, `docs/`, `--self-test` | crash evidence processing и reproducible self-check |
| Local speech-to-text | VoiceFlow | `voiceflow.py`, `docs/` | faster-whisper, CPU/CUDA, Windows input |
| Long AI/multimedia workflow | Video Translator Pro | `videotranslator/`, `tests/`, `tools/`, `AGENTS.md` | checkpoints, recovery, staged processing |
| Hybrid desktop/web | ZeTer OS | `app/`, `tools/check_project.py` | Python/native bridge + modular JavaScript frontend |
| Downloader/media pipeline | Universal Video Downloader | `src/`, `tests/`, `problem_log_validator.py` | format strategy, validation и diagnostics |

## 15 минут

### 1. Сравнить Web-архитектуры

- **ZeTer Photo Editor** — крупный browser application с rendering, format adapters, masks, typed pixel data и persistence.
- **ZAP ZONE** — realtime Three.js application с выделенными runtime/gameplay modules.
- **BizPilot** — local-first business application с тестируемым cash-flow engine, regression suite и диагностируемым headless browser boot.
- **CYBER RACE / Forest Hunter** — после modularization добавлен replay layer: seeded fixtures прогоняют последовательности AI/combat кадров детерминированно, а headless WebGL boot остаётся финальным integration gate.

### 2. Сравнить Python-архитектуры

- `Screen-Recorder-Pro/screen_recorder/` — модульное Windows multimedia-приложение;
- `Universal-Video-Downloader/src/` — downloader с отдельными tests/scripts/docs;
- `Video-Translator-Pro/videotranslator/` — package structure длительного pipeline;
- `ZeTer-OS/app/` — hybrid Python + JavaScript boundary;
- `Vacancy-Parser-Pro` — scraper / GUI / logging responsibilities.

### 3. Посмотреть verification strategy

Сравнить уровни доказательств:
1. **syntax/compile**;
2. **unit/regression**;
3. **integration/self-test**;
4. **browser smoke/runtime**;
5. **manual Windows / GPU / audio verification**.

Главный принцип: утверждение должно соответствовать тому уровню проверки, который реально выполнен.

## 30 минут

### A. Web graphics — ZeTer Photo Editor

Проверить:
- модель документа, layers/groups/masks;
- separation render state vs editable source;
- PSD/PSB import/export;
- 16/32-bit typed buffers;
- ICC/CMYK path;
- crash autosave;
- regression tests и CI.

### B. WebGL / AI — ZAP ZONE

Проверить:
- разделение engine / weapons / combat / entities / progression / runtime;
- tactical AI;
- ballistics и weapon handling;
- browser boot smoke test;
- performance/recovery contracts.

### C. Windows multimedia — Screen Recorder Pro

Проверить:
- FFmpeg command construction;
- capture/encoding selection;
- child-process lifecycle;
- capture recovery;
- save safety;
- что реально запускает GitHub Actions.

### D. System diagnostics — BSOD Investigator

Проверить:
- как dump/Event Log/driver data превращаются в evidence model;
- как отделяются сильные и слабые сигналы;
- историю независимых сбоев;
- safe self-test.

### E. Local AI — VoiceFlow

Проверить:
- audio → faster-whisper pipeline;
- CPU/CUDA paths;
- stable-fragment insertion;
- Windows input fallbacks;
- границу между CI-verifiable и hardware/runtime-dependent поведением.

## Что считать сильным сигналом

**Web:** state lifecycle, rendering budgets, module boundaries, graceful degradation, persistence, browser smoke tests.

**Python:** process lifecycle, WinAPI integration, recovery, external-tool validation, structured diagnostics.

**Для обоих направлений:** tests, CI, documentation, ограничение scope изменений и честное обозначение того, что ещё не проверено.

## Дополнительная навигация

- [Главный профиль](README.md)
- [Карта проектов](PROJECTS.md)
- [Инженерный подход](ENGINEERING.md)
- [Поддержка и диагностика](SUPPORT.md)
