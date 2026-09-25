**Язык / Language:** **Русский** · [English](README_EN.md)

# Дмитрий Колесниченко

### Python-разработчик · Web-разработчик

Создаю **веб-приложения и browser-first продукты** на HTML/CSS/JavaScript, Canvas/WebGL и Three.js, а также **Python-приложения для Windows**, инструменты автоматизации, мультимедийные системы и локальные AI-приложения.

Моё портфолио строится вокруг двух основных направлений: **Web Development** и **Python Development**. В обоих направлениях важны не только функции, но и архитектура, диагностика, восстановление после сбоев, автоматические проверки и сохранность пользовательских данных.

## Основные направления

| Направление | Что разрабатываю | Технологии |
|---|---|---|
| **Web Development** | браузерные приложения, local-first интерфейсы, графические редакторы, 2D/3D приложения и игры | JavaScript, HTML/CSS, Canvas 2D, WebGL, Three.js, Web Audio API, IndexedDB, localStorage |
| **Python Development** | Windows desktop, автоматизация, системные утилиты, мультимедиа, локальный AI | Python, Tkinter, WinAPI, ctypes, COM/SAPI, SQLite, FFmpeg, Whisper, CUDA |
| **Hybrid Desktop/Web** | desktop-приложения с JavaScript UI и Python/native bridge | Python, pywebview, JavaScript, local-first state, backup/recovery |

## Избранные проекты

| Проект | Направление | Что показывает |
|---|---|---|
| **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** | Web / Graphics | Canvas 2D, слои и маски, PSD/PSB, high-depth pixel pipeline, ICC/CMYK, regression tests |
| **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** | Web / 3D | Three.js/WebGL, modular JavaScript, tactical AI, оружие и баллистика, browser smoke testing |
| **[BizPilot](https://github.com/zeter1/BizPilot)** | Web / Application | local-first frontend, state model, localStorage, ZIP backup/restore |
| **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** | Python / Windows | FFmpeg, Desktop Duplication, NVENC, WinAPI, process management, recovery |
| **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** | Python / Diagnostics | WinDbg/CDB, crash dumps, Event Log, SQLite, evidence-based диагностика |
| **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** | Python / AI | faster-whisper, CPU/CUDA, real-time speech pipeline, Windows input |
| **[Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)** | Python / AI + Multimedia | Whisper → translation → TTS → FFmpeg, checkpoints, recovery |
| **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** | Hybrid | Python + JavaScript, pywebview bridge, local-first data, backup/recovery |

Полная карта проектов: **[PROJECTS.md](PROJECTS.md)**.

## Инженерный подход

- Ищу первопричину, а не маскирую симптом.
- Разделяю код по зонам ответственности.
- Проверяю не только код, но и конечный результат.
- Проектирую recovery для длинных операций.
- Считаю пользовательские данные частью архитектуры.
- AI-assisted изменения проверяю тестами и фактической валидацией.

Подробнее: **[ENGINEERING.md](ENGINEERING.md)**.

## Проверяемые точки входа

Чтобы технический reviewer мог быстро перейти от описания к коду и проверкам:

- **ZeTer Photo Editor:** [`src/adapters/`](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters) · [`tests/color-management.test.mjs`](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs) · [CI](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/.github/workflows/ci.yml).
- **ZAP ZONE:** [`src/core/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/core) · [`src/combat/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/combat) · [`src/weapons/`](https://github.com/zeter1/ZAP-ZONE/tree/main/src/weapons) · [structural validation](https://github.com/zeter1/ZAP-ZONE/blob/main/scripts/validate-structure.mjs) · [browser smoke CI](https://github.com/zeter1/ZAP-ZONE/blob/main/.github/workflows/validate.yml).
- **Screen Recorder Pro:** [`screen_recorder/`](https://github.com/zeter1/Screen-Recorder-Pro/tree/main/screen_recorder) · [capture recovery](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_capture_recovery.py) · [save safety](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_save_safety.py).
- **BSOD Investigator:** [`bsod_investigator.py`](https://github.com/zeter1/BSOD-Investigator/blob/main/bsod_investigator.py) · [`docs/`](https://github.com/zeter1/BSOD-Investigator/tree/main/docs).
- **VoiceFlow:** [`voiceflow.py`](https://github.com/zeter1/VoiceFlow/blob/main/voiceflow.py) · [`docs/`](https://github.com/zeter1/VoiceFlow/tree/main/docs).

## Технологии

**Web:** `HTML` · `CSS` · `JavaScript` · `Canvas 2D` · `WebGL` · `Three.js` · `Web Audio API` · `IndexedDB` · `localStorage`

**Python / Windows:** `Python` · `Tkinter` · `WinAPI` · `ctypes` · `COM / SAPI` · `pywebview` · `PyInstaller`

**AI / Multimedia:** `FFmpeg` · `FFprobe` · `yt-dlp` · `Whisper` · `faster-whisper` · `CUDA` · `Edge TTS`

**Data / Automation:** `SQLite` · `JSON` · `pandas` · `openpyxl` · `requests` · `BeautifulSoup`

**Engineering:** `Git` · `GitHub Actions` · regression tests · smoke tests · diagnostics · backup/recovery

## Навигация

- **[PROJECTS.md](PROJECTS.md)** — карта проектов.
- **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)** — технический маршрут на 5/15/30 минут.
- **[ENGINEERING.md](ENGINEERING.md)** — инженерные принципы и примеры.
- **[SUPPORT.md](SUPPORT.md)** — диагностика и bug reports для Web, Python и hybrid-проектов.

## Контакты

- **Email:** zeter11@gmail.com
- **Telegram:** https://t.me/zeter1
- **LinkedIn:** https://www.linkedin.com/in/zeter/
- **Сайт / портфолио:** https://dkl.do.am/
