**Язык / Language:** **Русский** · [English](PROJECTS_EN.md)

[Профиль](README.md) · [Программы](USER_GUIDE.md) · [Технический обзор](REVIEW_GUIDE.md) · [Поддержка](SUPPORT.md)

# Карта проектов

Здесь собраны проекты профиля и инженерные решения, которые можно изучить в коде. Основные направления — **Web Development** и **Python Development**; отдельно представлены гибридные приложения и новый видеоредактор. Для выбора, скачивания и запуска программы используйте **[пользовательский каталог](USER_GUIDE.md)**.

## Web Development

### [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)

**Что это:** браузерный графический редактор со слоями, масками, историей, non-destructive editing и PSD/PSB pipeline.

**Что смотреть:** Canvas 2D rendering/compositing, layers/groups, raster/vector masks, smart objects, PSD/PSB import/export, typed 16/32-bit pixel buffers, ICC/CMYK pipeline, IndexedDB crash autosave, regression tests и CI.

**Инженерный акцент:** сложная browser-side графика, сохранение precision, совместимость форматов и эволюция крупного JavaScript-приложения.

---

### [BizPilot](https://github.com/zeter1/BizPilot)

**Что это:** local-first рабочее пространство для малого бизнеса: клиенты, заказы, сделки, счета, финансы, заметки, календарь и аналитика.

**Что смотреть:** static frontend без обязательного backend, state model, `localStorage`, ZIP backup/restore, demo-data isolation, `js/cashflow.js`, regression tests денежного прогноза и реальный headless Chrome startup smoke.

**Инженерный акцент:** frontend architecture, state lifecycle и сохранность пользовательских данных. Browser smoke нашёл реальную latent startup-регрессию (`cashflowForecast is not defined`); root cause исправлен выделением тестируемого cash-flow engine и regression suite, после чего CI подтверждён зелёным runtime boot.

---

### [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)

**Что это:** браузерный 3D FPS 5×5 с союзными и вражескими AI-ботами.

**Что смотреть:** модульную структуру `src/`, Three.js/WebGL runtime, tactical/combat AI, weapon handling и ballistics, asset catalog, performance/recovery и headless browser smoke test.

**Инженерный акцент:** realtime browser gameplay, AI, modularization и runtime verification.

---

### [CYBER RACE](https://github.com/zeter1/CYBER-RACE)

**Что это:** браузерная 3D боевая гонка с AI-соперниками, оружием, бонусами и adaptive quality.

**Инженерный акцент:** Three.js/WebGL loop, Web Audio, AI, combat systems, performance adaptation и WebGL context recovery. После decomposition opponent frame/attack и homing kinematics стали dependency-injected simulation contracts. `tests/scenarios.mjs` с versioned seeded fixture replay-ит 180 кадров AI, серию attack decisions и 90 кадров homing rocket; затем CI поднимает настоящий headless WebGL boot.

---

### [Forest Hunter](https://github.com/zeter1/ForestHunter)

**Что это:** браузерный 3D FPS с охотой, progression, loot, contracts и AI-противниками.

**Инженерный акцент:** state-based AI, InstancedMesh, object pools, spatial collision grid и realtime entities. Boar state transitions, stochastic damage rolls, reload/deployable timelines и hit ordering теперь replayable contracts с injected RNG. Seeded scenario fixture проверяет 150 AI-кадров и combat timelines до headless WebGL integration gate; pointer lock, Web Audio и реальный GPU остаются отдельным proof layer.

## Python Development

### [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)

**Что это:** Windows-приложение для записи экрана, системного звука, микрофона и скриншотов.

**Что смотреть:** FFmpeg Desktop Duplication, NVENC, CoreAudio loopback fallback, child-process lifecycle, modular `screen_recorder/`, capture recovery, save safety и project verification.

---

### [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)

**Что это:** инструмент расследования причин BSOD по crash dumps, Event Log и данным драйверов.

**Что смотреть:** CDB/WinDbg, evidence model, crash fingerprints, SQLite history, self-test и CI.

---

### [VoiceFlow](https://github.com/zeter1/VoiceFlow)

**Что это:** локальный speech-to-text для ввода текста в активное поле Windows-приложения.

**Что смотреть:** faster-whisper, CPU/CUDA paths, background pipeline, Windows input и diagnostics.

---

### [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)

**Что это:** Whisper → translation → TTS → FFmpeg pipeline для перевода и переозвучивания видео.

**Что смотреть:** checkpoints, persistent cache, bounded retry, recovery и final artifact validation.

---

### [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)

**Что это:** multi-source aggregation вакансий с filtering, deduplication и Excel export.

**Что смотреть:** source adapters, fault isolation, normalisation/deduplication и offline regression tests.

---

### [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)

**Что это:** загрузка MP4/MP3 с compatibility-first стратегией.

**Что смотреть:** yt-dlp format selection, remux/transcoding fallback, ffprobe validation, modular `src/`, tests и code map.

---

### [ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter)

**Что это:** Windows-приложение для конвертации видеокурсов в MP3 пофайлово и по частям до 10 часов, а также объединения видео в MP4-части.

**Что смотреть:** Tkinter UI, `videovaudio/audio/`, `videovaudio/video/`, `process_runner.py` (запуск FFmpeg, отмена и таймауты), `diagnostics/`, `tools/test_audio_regressions.py`, [Windows EXE CI](https://github.com/zeter1/ZeTer-Media-Converter/blob/main/.github/workflows/build-windows.yml).

**Инженерный акцент:** резервные копии прежних MP3 с manifest, проверка результатов до публикации, структурированная диагностика и автономная сборка со сверкой SHA-256. [Релиз v3.3.5](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5). GUI и многочасовые сценарии требуют ручной проверки.

---

### [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)

**Что это:** Windows TTS + MP3.

**Что смотреть:** Microsoft SAPI/COM, global hotkeys, state persistence и long-job recovery.

---

### [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)

**Что это:** системная Windows-утилита для блокировки и управления режимом сна.

**Что смотреть:** WinAPI, WTS API, mutex, power management, self-test и bounded logging.

## Hybrid Desktop/Web

### [ZeTer OS](https://github.com/zeter1/ZeTer-OS)

**Что это:** локальное рабочее пространство с Python desktop shell и JavaScript frontend.

**Что смотреть:** pywebview bridge, modular frontend, local-first state, backup/recovery и project-level verification.

## Desktop / Video

### [Zeter Video Editor](https://github.com/zeter1/zeter-video-editor)

**Что это:** Windows-видеоредактор с многодорожечной временной шкалой и локальными проектами на Tauri, React, TypeScript, Rust и FFmpeg.

**Что смотреть:** [README](https://github.com/zeter1/zeter-video-editor#readme), [PROJECT_STATUS.md](https://github.com/zeter1/zeter-video-editor/blob/main/PROJECT_STATUS.md) и [package.json](https://github.com/zeter1/zeter-video-editor/blob/main/apps/desktop/package.json). Проект проходит подготовку к выпуску; готового публичного GitHub-релиза пока нет. Текущий статус реализации и проверки определяет PROJECT_STATUS.md.

## Как смотреть портфолио

Если времени мало:
1. **ZeTer Photo Editor** — глубокая browser-side инженерия.
2. **ZAP ZONE** — WebGL, modular JavaScript и AI.
3. **Screen Recorder Pro** — Python/Windows/multimedia и recovery.
4. **BSOD Investigator** — diagnostics и evidence handling.
5. **VoiceFlow** — local AI.
6. **BizPilot** — local-first web architecture.
7. **ZeTer OS** — hybrid Python + JavaScript.

Для конкретных точек входа и уровней проверки: **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)**.
