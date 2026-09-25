**Язык / Language:** **Русский** · [English](README_EN.md)

# Дмитрий Колесниченко

### Python-разработчик · Web-разработчик · Windows/Desktop · Автоматизация

Разрабатываю **веб-приложения и браузерные продукты** на HTML/CSS/JavaScript, 2D/3D-интерфейсы на Canvas/WebGL, а также **Python-приложения для Windows**, инструменты автоматизации, мультимедийные и локальные AI-системы. Веб-разработка и Python-разработка — два основных направления моего портфолио.

В проектах стараюсь доводить идею дальше рабочего прототипа: разделяю код по зонам ответственности, добавляю диагностику, восстановление после сбоев, автоматические проверки, безопасную работу с пользовательскими данными и документацию, по которой проект можно понять без чтения всего исходного кода.

## Быстрая навигация

- **[PROJECTS.md](PROJECTS.md)** — подробная карта проектов: что решает каждый проект и какие инженерные решения в нём смотреть.
- **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)** — маршрут технического просмотра портфолио на 5, 15 или 30 минут с конкретными файлами и проверками.
- **[ENGINEERING.md](ENGINEERING.md)** — мой инженерный подход: надёжность, диагностика, восстановление, тестирование и AI-assisted development.
- **[SUPPORT.md](SUPPORT.md)** — как правильно сообщать о проблемах и какие диагностические данные полезны в разных проектах.

Если нужно быстро оценить технический диапазон, рекомендую начать с **ZeTer Photo Editor → ZAP ZONE → Screen Recorder Pro → BSOD Investigator → VoiceFlow → BizPilot → ZeTer OS**.

## Ключевая специализация

- **Web / frontend** — HTML, CSS, JavaScript, Canvas 2D, WebGL, Three.js, Web Audio API, IndexedDB/localStorage, адаптивные интерфейсы и локальные browser-first приложения без обязательного backend.
- **Python / Windows desktop** — Tkinter, WinAPI, ctypes, COM/SAPI, системный трей, глобальные горячие клавиши, автозапуск и интеграция с Windows.
- **Мультимедиа** — FFmpeg, FFprobe, yt-dlp, запись экрана, обработка аудио и видео, remux/transcoding, аппаратное кодирование NVENC.
- **Speech / AI** — Whisper, faster-whisper, Edge TTS, локальное распознавание речи, CPU/CUDA-пайплайны.
- **Автоматизация и данные** — SQLite, JSON, pandas, openpyxl, requests, BeautifulSoup, экспорт и локальные рабочие процессы.
- **Гибридные приложения** — Python + pywebview + HTML/CSS/JavaScript, native bridge и локальное хранение состояния.
- **Надёжность** — тайм-ауты, retry-стратегии, checkpoint/recovery, управление подпроцессами, резервные копии, структурированные логи и self-tests.
- **AI-assisted engineering** — использую ChatGPT и Codex для анализа, рефакторинга и ускорения разработки, а изменения проверяю тестами, статическими проверками и ручной валидацией там, где это необходимо.

## Проекты

| Проект | Задача | Ключевые инженерные темы |
|---|---|---|
| **[ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor)** | Браузерный графический редактор со слоями, масками и PSD/PSB pipeline | Canvas 2D, JavaScript, layered document model, typed 16/32-bit pixel buffers, PSD/PSB, ICC/CMYK, regression tests |
| **[BizPilot](https://github.com/zeter1/BizPilot)** | Local-first рабочее пространство для малого бизнеса | HTML/CSS/JavaScript, localStorage, бизнес-модель данных, ZIP backup/restore, статический frontend без backend |
| **[ZAP ZONE](https://github.com/zeter1/ZAP-ZONE)** | Браузерный 3D FPS 5×5 с AI-ботами | Three.js/WebGL, modular JavaScript, tactical AI, оружие/баллистика, assets pipeline, headless browser smoke test |
| **[CYBER RACE](https://github.com/zeter1/CYBER-RACE)** | Браузерная 3D боевая гонка | Three.js/WebGL, AI-соперники, оружие, Web Audio, адаптивное качество и восстановление WebGL-контекста |
| **[Forest Hunter](https://github.com/zeter1/ForestHunter)** | Браузерный 3D FPS с охотой, прогрессией и AI | Three.js/WebGL, state-based AI, InstancedMesh, object pools, spatial collisions, gameplay systems |
| **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** | Запись экрана, системного звука, микрофона и скриншотов | FFmpeg, Desktop Duplication, NVENC, WinAPI hotkeys, управление процессами, модульная архитектура |
| **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** | Расследование причин BSOD в Windows | WinDbg/CDB, crash dumps, Event Log, анализ драйверов, SQLite, evidence-based диагностика |
| **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** | Локальный голосовой ввод в любое приложение | faster-whisper, CUDA/CPU, real-time pipeline, Windows input, фоновые задачи, privacy-first подход |
| **[Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)** | Распознавание, перевод и озвучивание видео | Whisper, TTS, FFmpeg, checkpoints, recovery, кэширование, устойчивые длительные пайплайны |
| **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** | Локальное рабочее пространство с заметками, задачами, файлами и инструментами | Python + JavaScript, pywebview bridge, local-first data, backup/recovery, модульный frontend |
| **[Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)** | Агрегация вакансий из нескольких источников | HTTP/parsing, адаптеры источников, фильтрация, дедупликация, Excel, fault isolation |
| **[Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)** | Загрузка видео и аудио с приоритетом совместимого результата | yt-dlp, FFmpeg/ffprobe, MP4 до 1080p, remux/transcoding fallback, диагностика |
| **[Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)** | Озвучивание текста и создание MP3 | Microsoft SAPI, COM, глобальные hotkeys, восстановление длительных заданий |
| **[Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)** | Блокировка Windows без остановки длительных фоновых задач | WinAPI, WTS API, power management, mutex, компактная диагностика |

## Инженерные доказательства

В профиле стараюсь отделять утверждение от его доказательства. Ниже — короткие точки входа для технического просмотра.

| Инженерная тема | Где смотреть | Что можно проверить |
|---|---|---|
| **Recovery и защита результата** | `Screen-Recorder-Pro/verify_capture_recovery.py`, `verify_save_safety.py`, `screen_recorder/` | поведение при сбоях FFmpeg, остановке и частично созданном результате |
| **Regression / structural verification** | `Screen-Recorder-Pro/verify_project.py`, `Universal-Video-Downloader/tests/`, `Vacancy-Parser-Pro/tests/` | реальные автоматические проверки вместо только ручного smoke-test |
| **Evidence-based диагностика** | `BSOD-Investigator`, `Vacancy-Parser-Pro/problem_logging.py`, `Universal-Video-Downloader/problem_log_validator.py` | как диагностический контекст превращается в воспроизводимое расследование |
| **Local AI pipeline** | `VoiceFlow/voiceflow.py`, `Video-Translator-Pro/videotranslator/` | CPU/CUDA, speech-to-text, этапность и recovery длительной обработки |
| **Hybrid desktop/web** | `ZeTer-OS/app/`, `tools/check_project.py` | native bridge, frontend-модули и project-level verification |
| **Browser graphics / image pipeline** | `ZeTer-Photo-Editor` | Canvas rendering, слои/маски, PSD/PSB, high-depth typed buffers и color-management pipeline |
| **WebGL / browser game systems** | `ZAP-ZONE`, `CYBER-RACE`, `ForestHunter` | Three.js, AI, real-time loop, управление ресурсами, графика и производительность в браузере |
| **Local-first web application** | `BizPilot` | browser state model, persistence, backup/restore и frontend без обязательного сервера |
| **CI и безопасная автоматизация** | `.github/workflows/` в основных репозиториях | compile/test/self-test gates, Windows runners, external-tool validation |

Подробный маршрут с конкретными файлами и уровнями доказательств: **[REVIEW_GUIDE.md](REVIEW_GUIDE.md)**.

## Карта компетенций по репозиториям

| Направление | Где это видно |
|---|---|
| **Web / Frontend applications** | ZeTer Photo Editor, BizPilot, ZAP ZONE, CYBER RACE, Forest Hunter |
| **Canvas 2D / browser imaging** | ZeTer Photo Editor |
| **Three.js / WebGL / browser games** | ZAP ZONE, CYBER RACE, Forest Hunter |
| **Windows API и системная интеграция** | Screen Recorder Pro, BSOD Investigator, VoiceFlow, Windows PC Locker, Text to MP3 |
| **Мультимедийные пайплайны** | Screen Recorder Pro, Video Translator Pro, Universal Video Downloader, Text to MP3 |
| **Локальный AI / Speech** | VoiceFlow, Video Translator Pro |
| **Долгие и отказоустойчивые задачи** | Video Translator Pro, Screen Recorder Pro, Text to MP3 |
| **Диагностика и поиск первопричин** | BSOD Investigator, Screen Recorder Pro, Vacancy Parser Pro, Windows PC Locker |
| **Парсинг и сетевые интеграции** | Vacancy Parser Pro, Universal Video Downloader |
| **Desktop + Web архитектура** | ZeTer OS |
| **Автоматические проверки и CI** | Несколько проектов содержат GitHub Actions, self-tests, smoke-тесты или собственные проверяющие скрипты |

## Что можно оценить по моим репозиториям

**Не только happy path.** В приложениях отдельно прорабатываю тайм-ауты, отмену операций, ошибки внешних процессов, сетевые сбои и восстановление после прерывания.

**Диагностику реальных проблем.** Для сложных приложений создаю структурированные диагностические данные, которые позволяют быстрее понять первопричину вместо накопления огромных неструктурированных логов.

**Архитектуру под дальнейшие изменения.** Большие программы разделяю на модули, документирую зоны ответственности и добавляю карты проекта или проверки структуры там, где код активно развивается.

**Работу с пользовательскими данными.** Локальное состояние, резервные копии, восстановление и исключение runtime-данных из Git рассматриваю как часть приложения, а не как второстепенную деталь.

**Проверку изменений.** Использую синтаксические проверки, self-tests, regression tests, smoke-тесты и CI. Аппаратно-зависимые сценарии дополнительно проверяются вручную в Windows.

Подробнее: **[инженерный подход и примеры из проектов](ENGINEERING.md)**.

## Как быстро посмотреть проекты

В README каждого основного репозитория есть:

1. назначение и ключевые возможности;
2. инструкция по установке;
3. команда запуска;
4. пошаговое использование;
5. описание архитектуры или важных инженерных решений;
6. раздел о диагностике, надёжности или ограничениях проекта.

Для более глубокого просмотра в крупных проектах используются каталоги `docs/`, карты кода, проверяющие скрипты, тесты и CI-конфигурации.

## Подход к разработке

**Сначала задача пользователя, затем технология.** Архитектура и интерфейс должны помогать решать задачу, а не демонстрировать сложность ради сложности.

**Ищу первопричину, а не маскирую симптом.** Для сложных сбоев добавляю диагностический контекст, воспроизводимые шаги и компактные структурированные логи.

**Длительные операции должны переживать реальные сбои.** Использую контрольные точки, ограниченные повторы, тайм-ауты, безопасное завершение процессов и восстановление промежуточного результата.

**Код должен быть удобен для следующего изменения.** Разделяю большие приложения на зоны ответственности, документирую архитектурные контракты и добавляю автоматические проверки против регрессий.

**ИИ — ускоритель, а не замена инженерной проверке.** Результат AI-assisted разработки проверяется теми же способами, что и любые другие изменения кода.

## Технологии

`Python` · `HTML` · `CSS` · `JavaScript` · `Canvas 2D` · `WebGL` · `Three.js` · `Web Audio API` · `IndexedDB` · `localStorage` · `Tkinter` · `WinAPI` · `ctypes` · `COM / SAPI` · `FFmpeg` · `FFprobe` · `yt-dlp` · `Whisper` · `faster-whisper` · `CUDA` · `Edge TTS` · `SQLite` · `pandas` · `openpyxl` · `requests` · `BeautifulSoup` · `pywebview` · `Git` · `GitHub Actions` · `PyInstaller`

## Обо мне

Мои опубликованные проекты охватывают два основных направления: **Web-разработку** — браузерные приложения, Canvas/WebGL, local-first интерфейсы и 3D-игры — и **Python-разработку** — Windows desktop, автоматизацию, мультимедиа, системные утилиты и локальные AI-инструменты.

Мне интересен полный жизненный цикл программы: от идеи и первого рабочего прототипа до рефакторинга, диагностики реальных проблем, улучшения UX, тестирования и подготовки проекта к дальнейшему сопровождению.

## Контакты

- **Email:** zeter11@gmail.com
- **Telegram:** https://t.me/zeter1
- **LinkedIn:** https://www.linkedin.com/in/zeter/
- **Сайт / портфолио:** https://dkl.do.am/
