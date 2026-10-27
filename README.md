**Язык / Language:** **Русский** · [English](README_EN.md)

# Дмитрий Колесниченко

### Python-разработчик · Web-разработчик

Создаю **веб-приложения и browser-first продукты** на HTML/CSS/JavaScript, Canvas/WebGL и Three.js, а также **Python-приложения для Windows**, инструменты автоматизации, мультимедийные системы и локальные AI-приложения.

Здесь можно выбрать программу под свою задачу, найти инструкции и посмотреть, как она устроена. Основные направления — **Web Development** и **Python Development**: браузерные инструменты и игры, Windows-приложения, автоматизация и мультимедиа.

**Для пользователей:** [выбор, скачивание и запуск](USER_GUIDE.md). **Для работодателей:** [код, архитектура и проверки за 5/15/30 минут](REVIEW_GUIDE.md). **Портфолио и веб-демо:** [открыть сайт](https://dkl.do.am/).

На этой странице: [выбрать программу](#что-хотите-сделать) · [посмотреть инженерные решения](#для-работодателей-и-технических-специалистов) · [все проекты](#все-проекты).

**Обсудить работу или проект:**

- [https://t.me/zeter1](https://t.me/zeter1)
- [zeter11@gmail.com](mailto:zeter11@gmail.com)

**Сообщить об ошибке:** [как подготовить отчёт](SUPPORT.md).

## Что хотите сделать?

| Задача | Проект | С чего начать |
|---|---|---|
| Редактировать фотографии и работать со слоями | [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) | [Открыть онлайн](https://dkl.do.am/servisi/PhotoEditor/index.html) · [Как начать](https://github.com/zeter1/ZeTer-Photo-Editor#попробовать-редактор) |
| Вести клиентов, задачи и финансы бизнеса | [BizPilot](https://github.com/zeter1/BizPilot) | [Запустить онлайн](https://dkl.do.am/portfolio/bizpilot/index.html) · [Инструкция](https://github.com/zeter1/BizPilot#запуск) |
| Записать экран, звук или сделать скриншот | [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) | [Windows-сборки](https://github.com/zeter1/Screen-Recorder-Pro/releases) |
| Надиктовать текст вместо печати | [VoiceFlow](https://github.com/zeter1/VoiceFlow) | [Windows-сборки](https://github.com/zeter1/VoiceFlow/releases) |
| Перевести и озвучить видео | [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro) | [Windows-сборки](https://github.com/zeter1/Video-Translator-Pro/releases) |
| Скачать видео в MP4 до 1080p и получить MP3 | [ZeTer Video Downloader](https://github.com/zeter1/ZeTer-Video-Downloader) | [Windows-сборки](https://github.com/zeter1/ZeTer-Video-Downloader/releases) |
| Преобразовать видеокурс в MP3 или объединить видео по 10 часов | [ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter) | [Скачать Windows EXE v3.3.5](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5) |
| Собрать вакансии и выгрузить их в Excel | [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro) | [Windows-сборки](https://github.com/zeter1/Vacancy-Parser-Pro/releases) |
| Организовать заметки и задачи | [ZeTer OS](https://github.com/zeter1/ZeTer-OS) | [Запустить онлайн](https://dkl.do.am/zeteros/index.html) · [Windows-сборки](https://github.com/zeter1/ZeTer-OS/releases) |
| Поиграть в браузере | [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE), [CYBER RACE](https://github.com/zeter1/CYBER-RACE), [Forest Hunter](https://github.com/zeter1/ForestHunter) | [Запуск и требования](USER_GUIDE.md#браузерные-приложения-и-игры) |

**Перед скачиванием Windows-приложения:** откройте страницу Releases нужного проекта и проверьте, является ли сборка обычным релизом или помечена **Pre-release**. У **ZeTer Media Converter v3.3.5** есть обычный [Windows EXE-релиз](https://github.com/zeter1/ZeTer-Media-Converter/releases/tag/v3.3.5). Другим приложениям могут понадобиться FFmpeg, модель AI, драйверы или доступ к внешнему сервису — требования уточняйте в README проекта.

Полный пользовательский каталог, включая загрузку видео, озвучку текста и диагностику Windows: **[USER_GUIDE.md](USER_GUIDE.md)**.

**Проверка безопасности перед запуском:** скачивайте установщики только из раздела **Releases** указанного репозитория; проверьте издателя, версию и системные требования. Если у релиза нет цифровой подписи или опубликованной контрольной суммы, не считайте происхождение бинарного файла криптографически подтверждённым. Не отключайте SmartScreen/антивирус только ради запуска и не запускайте непроверенные EXE с правами администратора.

## Для работодателей и технических специалистов

Три примера для первого знакомства — от задачи пользователя к решению и его проверке:

| Проект и задача | Инженерное решение | Что изучить |
|---|---|---|
| **BizPilot** — планировать деньги малого бизнеса | Расчёты денежного потока отделены от интерфейса; тесты разбирают просроченные счета и отрицательный остаток. | [Модуль расчётов](https://github.com/zeter1/BizPilot/blob/main/js/cashflow.js) · [регрессионные сценарии](https://github.com/zeter1/BizPilot/blob/main/scripts/test-cashflow.mjs) · [результаты CI](https://github.com/zeter1/BizPilot/actions) |
| **Screen Recorder Pro** — записывать экран и сохранять результат | Управление процессами FFmpeg, восстановление захвата и защита уже созданных файлов при сохранении. | [Модули приложения](https://github.com/zeter1/Screen-Recorder-Pro/tree/main/screen_recorder) · [проверки сохранения](https://github.com/zeter1/Screen-Recorder-Pro/blob/main/verify_save_safety.py) · [результаты CI](https://github.com/zeter1/Screen-Recorder-Pro/actions) |
| **ZeTer Photo Editor** — редактировать изображения со слоями | Адаптеры графических форматов и отдельные проверки управления цветом. | [Адаптеры](https://github.com/zeter1/ZeTer-Photo-Editor/tree/main/src/adapters) · [цветовые сценарии](https://github.com/zeter1/ZeTer-Photo-Editor/blob/main/tests/color-management.test.mjs) · [результаты CI](https://github.com/zeter1/ZeTer-Photo-Editor/actions) |

Для других направлений и более подробного просмотра: **[маршрут на 5/15/30 минут](REVIEW_GUIDE.md)**. Ссылки «результаты CI» ведут к запускам **GitHub Actions**: сверяйте ветку, commit и выполненные проверки. Зелёный запуск другой ревизии не подтверждает текущий код или скачанную сборку.

Разрабатываю с помощью ChatGPT/Codex; изменения проверяю по diff, автоматическими проверками и ручными сценариями там, где нужен браузер, Windows или оборудование. Наличие тестов в репозитории не означает, что все пользовательские сценарии проверены на любом компьютере.

## Основные направления

| Направление | Что разрабатываю | Технологии |
|---|---|---|
| **Web Development** | браузерные приложения, local-first интерфейсы, графические редакторы, 2D/3D приложения и игры | JavaScript, HTML/CSS, Canvas 2D, WebGL, Three.js, Web Audio API, IndexedDB, localStorage |
| **Python Development** | Windows desktop, автоматизация, системные утилиты, мультимедиа, локальный AI | Python, Tkinter, WinAPI, ctypes, COM/SAPI, SQLite, FFmpeg, Whisper, CUDA |
| **Hybrid Desktop/Web** | desktop-приложения с JavaScript UI и Python/native bridge | Python, pywebview, JavaScript, local-first state, backup/recovery |

## Все проекты

Ниже — проекты и технические решения, которые можно изучить в их репозиториях. Пользовательские инструкции собраны отдельно в **[USER_GUIDE.md](USER_GUIDE.md)**.

| Проект | Направление | Что показывает |
|---|---|---|
| **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** | Web / Graphics | браузерный графический редактор: Canvas 2D, layers/masks, PSD/PSB, high-depth pixel pipeline, ICC/CMYK, regression tests |
| **[BizPilot](https://github.com/zeter1/BizPilot)** | Web / Application | local-first бизнес-приложение, testable cash-flow engine, localStorage/ZIP backup, regression tests и real headless-browser boot smoke |
| **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** | Web / 3D | Three.js/WebGL FPS, modular JavaScript, tactical AI, оружие/баллистика, structural validation и browser smoke CI |
| **[CYBER RACE](https://github.com/zeter1/CYBER-RACE)** | Web / 3D | Three.js/WebGL combat racing; dependency-injected opponent/ballistics simulation, seeded replay fixtures, Node contracts и headless WebGL integration CI |
| **[Forest Hunter](https://github.com/zeter1/ForestHunter)** | Web / 3D | Three.js FPS; replayable boar state machine, seeded combat/reload/deployable scenarios, environment modules, Node contracts и headless WebGL CI |
| **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** | Python / Windows | FFmpeg, Desktop Duplication, NVENC, WinAPI, process lifecycle, capture recovery и save safety |
| **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** | Python / Diagnostics | WinDbg/CDB, crash dumps, Event Log, SQLite и evidence-based диагностика |
| **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** | Python / AI | local speech-to-text, faster-whisper, CPU/CUDA, background pipeline и Windows input |
| **[Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)** | Python / AI + Multimedia | Whisper → translation → TTS → FFmpeg, checkpoints, cache, recovery и artifact validation |
| **[Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)** | Python / Automation | multi-source парсинг вакансий, adapters, fault isolation, deduplication и Excel export |
| **[ZeTer Video Downloader](https://github.com/zeter1/ZeTer-Video-Downloader)** | Python / Multimedia | yt-dlp, MP4/MP3, format selection, remux/transcoding fallback, ffprobe validation и tests |
| **[ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter)** | Python / Windows · Multimedia | Tkinter, FFmpeg/FFprobe, видео → MP3, объединение MP4 до 10 часов, резервирование MP3, диагностика, регрессионные тесты, Windows EXE CI |
| **[Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)** | Python / Windows | Microsoft SAPI/COM, Windows TTS, MP3, global hotkeys, state persistence и long-job recovery |
| **[Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)** | Python / Windows | WinAPI, WTS API, mutex, power management, self-test и bounded logging |
| **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** | Hybrid Desktop/Web | Python + JavaScript, pywebview bridge, modular frontend, local-first state и backup/recovery |
| **[Zeter Video Editor](https://github.com/zeter1/zeter-video-editor)** | Desktop / Video | Tauri, React, TypeScript, Rust и FFmpeg; многодорожечный монтаж, локальные проекты; подготовка к выпуску, готового GitHub-релиза пока нет |

Расширенная техническая карта всех проектов: **[PROJECTS.md](PROJECTS.md)**.

## Инженерный подход

- Ищу первопричину, а не маскирую симптом.
- Разделяю код по зонам ответственности.
- Проверяю не только код, но и конечный результат.
- Проектирую recovery для длинных операций.
- Считаю пользовательские данные частью архитектуры.
- AI-assisted изменения проверяю тестами и фактической валидацией.

Подробнее: **[ENGINEERING.md](ENGINEERING.md)**.

## Проверяемые точки входа

<details>
<summary>Развернуть ссылки на код, тесты и CI</summary>

Чтобы технический reviewer мог быстро перейти от описания к коду и проверкам:

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

## Технологии

<details>
<summary>Развернуть полный список технологий</summary>

**Web:** `HTML` · `CSS` · `JavaScript` · `Canvas 2D` · `WebGL` · `Three.js` · `Web Audio API` · `IndexedDB` · `localStorage`

**Python / Windows:** `Python` · `Tkinter` · `WinAPI` · `ctypes` · `COM / SAPI` · `pywebview` · `PyInstaller`

**AI / Multimedia:** `FFmpeg` · `FFprobe` · `yt-dlp` · `Whisper` · `faster-whisper` · `CUDA` · `Edge TTS`

**Data / Automation:** `SQLite` · `JSON` · `pandas` · `openpyxl` · `requests` · `BeautifulSoup`

**Engineering:** `Git` · `GitHub Actions` · regression tests · smoke tests · diagnostics · backup/recovery

</details>

## Навигация

- **[USER_GUIDE.md](USER_GUIDE.md)** — выбор программы, скачивание и запуск.
- **[PROJECTS.md](PROJECTS.md)** — карта проектов.
- **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)** — технический маршрут на 5/15/30 минут.
- **[ENGINEERING.md](ENGINEERING.md)** — инженерные принципы и примеры.
- **[SUPPORT.md](SUPPORT.md)** — диагностика и bug reports для Web, Python и hybrid-проектов.
- **[CONTRIBUTING.md](CONTRIBUTING.md)** — как подготовить воспроизводимое исправление, тесты и pull request.

## Контакты для связи:

- [zeter11@gmail.com](mailto:zeter11@gmail.com)
- [https://t.me/zeter1](https://t.me/zeter1)
- [https://www.linkedin.com/in/zeter/](https://www.linkedin.com/in/zeter/)
- [https://www.facebook.com/zeter1](https://www.facebook.com/zeter1)
- [https://vk.ru/zeter1](https://vk.ru/zeter1)
- [https://www.instagram.com/zeter1992/](https://www.instagram.com/zeter1992/)
- [https://tenchat.ru/zeter](https://tenchat.ru/zeter)
- [https://x.com/zeter1](https://x.com/zeter1)
- [https://www.threads.com/@zeter1992](https://www.threads.com/@zeter1992)
- [https://ok.ru/zeter1](https://ok.ru/zeter1)
- [https://t.me/zeterchat](https://t.me/zeterchat) — Telegram-группа: обо мне, проекты и чат
- [https://dkl.do.am/](https://dkl.do.am/) — сайт-портфолио и веб-проекты
