**Язык / Language:** **Русский** · [English](PROJECTS_EN.md)

# Карта проектов

Здесь перечислены **все 14 проектных репозиториев** профиля (без служебного `zeter1/zeter1`). Портфолио разделено на два основных направления — **Web Development** и **Python Development**. Ниже — не просто список репозиториев, а карта того, какие инженерные решения в каждом проекте стоит смотреть.

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

**Инженерный акцент:** Three.js/WebGL loop, Web Audio, AI, combat systems, performance adaptation и WebGL context recovery. Deep Gameplay Decomposition вынес track/environment, lap state, opponent lane/rubber-band/lead math, collision/ballistics и HUD/minimap в отдельные modules. `tests/contracts.mjs` проверяет deterministic gameplay contracts под Node; structural validation и headless WebGL boot проходят Actions.

---

### [Forest Hunter](https://github.com/zeter1/ForestHunter)

**Что это:** браузерный 3D FPS с охотой, progression, loot, contracts и AI-противниками.

**Инженерный акцент:** state-based AI, InstancedMesh, object pools, spatial collision grid и управление realtime-объектами. Deep Gameplay Decomposition вынес environment ownership, boar AI policy, weapon/reload/deployable math, collision geometry, XP/upgrades и HUD model. Node contract tests + structural validation + headless WebGL boot проходят CI; pointer lock, Web Audio, GPU performance и полный gameplay остаются отдельным уровнем proof.

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
