# Гайд по техническому просмотру портфолио

Этот файл помогает быстро понять, **где именно** в репозиториях находятся показательные инженерные решения. Он не заменяет README отдельных проектов: цель — дать reviewer короткий маршрут от утверждения к коду, тесту или проверке.

## 5 минут

Если времени мало, достаточно открыть четыре проекта и сразу перейти к указанным точкам:

1. **[Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)** — `screen_recorder/`, `verify_project.py`, `verify_capture_recovery.py`, `verify_save_safety.py`, `.github/workflows/validate.yml`.
2. **[BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)** — `bsod_investigator.py`, встроенный `--self-test`, `.github/workflows/ci.yml`, `docs/`.
3. **[VoiceFlow](https://github.com/zeter1/VoiceFlow)** — `voiceflow.py`, `docs/`, `.github/workflows/python-check.yml`.
4. **[ZeTer OS](https://github.com/zeter1/ZeTer-OS)** — `app/`, `tools/check_project.py`, `problem_logs.py`, `.github/workflows/ci.yml`.

Этого достаточно, чтобы увидеть Windows desktop, мультимедиа, системную диагностику, local AI, hybrid desktop/web и подход к автоматической проверке.

## Карта инженерных доказательств

| Что хочется проверить | Проект | Куда смотреть | Что это показывает |
|---|---|---|---|
| Управление длительной мультимедийной операцией | Screen Recorder Pro | `screen_recorder/`, `verify_capture_recovery.py`, `verify_save_safety.py` | lifecycle внешнего FFmpeg-процесса, recovery и защита результата |
| Реальные regression/structural checks | Screen Recorder Pro | `verify_project.py`, `verify_recording_publication.py`, `.github/workflows/validate.yml` | автоматическая проверка архитектурных и пользовательских инвариантов |
| Evidence-based диагностика Windows | BSOD Investigator | `bsod_investigator.py`, `docs/`, `--self-test` | обработка dump/event/driver evidence и воспроизводимая self-check логика |
| Local speech-to-text pipeline | VoiceFlow | `voiceflow.py`, `docs/` | faster-whisper, CPU/CUDA path, Windows input и фоновые операции |
| Надёжный видео-download pipeline | Universal Video Downloader | `src/`, `tests/`, `problem_log_validator.py` | разделение downloader/format/diagnostics логики и offline regression tests |
| Долгий AI/multimedia pipeline | Video Translator Pro | `videotranslator/`, `tests/`, `tools/`, `AGENTS.md` | checkpoints, recovery, обработка этапов и AI-friendly структура |
| Парсинг нескольких источников | Vacancy Parser Pro | `job_scraper.py`, `problem_logging.py`, `tests/` | fault isolation, normalisation/deduplication и диагностика источников |
| Hybrid desktop/web architecture | ZeTer OS | `app/`, `tools/check_project.py`, `problem_logs.py` | Python/native bridge + JavaScript UI + project verification |
| Windows system utility safety | Windows PC Locker | `computer_locker.pyw`, `--self-test`, `.github/workflows/windows-checks.yml` | WinAPI/WTS/power-management path и безопасный self-test |
| Windows TTS / long-running jobs | Text to MP3 | `text_to_mp3.py`, `.github/workflows/python-check.yml` | SAPI/COM pipeline и Windows-specific application logic |

## 15 минут

### 1. Архитектура

Сравнить, как проекты разного возраста организованы по зонам ответственности:

- `Screen-Recorder-Pro/screen_recorder/` — модульное desktop-приложение;
- `Universal-Video-Downloader/src/` — downloader с отдельными tests/scripts/docs;
- `Video-Translator-Pro/videotranslator/` — пакетная структура длительного pipeline;
- `ZeTer-OS/app/` — hybrid frontend/backend;
- `Vacancy-Parser-Pro` — раздельные scraper / GUI / logging слои.

Для `BSOD-Investigator`, `VoiceFlow` и `Text-to-MP3-Windows` полезно также обратить внимание на размер текущего legacy entry module: это реальные рабочие приложения, для которых дальнейшая декомпозиция остаётся отдельной инженерной задачей, а не скрывается маркетинговым описанием.

### 2. Надёжность длительных операций

Посмотреть:

- checkpoints и recovery в `Video-Translator-Pro`;
- управление FFmpeg и восстановление записи в `Screen-Recorder-Pro`;
- восстановление длительных TTS/MP3-задач в `Text-to-MP3-Windows`;
- timeout/retry/fallback обработку в сетевых частях `Universal-Video-Downloader` и `Vacancy-Parser-Pro`.

### 3. Диагностика

Обратить внимание, что логи используются как инструмент поиска первопричины:

- `BSOD-Investigator` — диагностические отчёты и история анализа;
- `Vacancy-Parser-Pro/problem_logging.py` — контекст проблем источников;
- `Universal-Video-Downloader/problem_log_validator.py` и каталог `Логи проблем/` — схема и проверка качества diagnostic artifacts;
- `ZeTer-OS/problem_logs.py` — централизованный problem-log слой;
- `Screen-Recorder-Pro/screen_recorder/mixins/problem_logs.py` — диагностика внутри multimedia application lifecycle.

## 30 минут

### A. Real-time multimedia — Screen Recorder Pro

Проверить:

- формирование FFmpeg-команд;
- выбор GPU/CPU capture и encoding path;
- системный звук и fallback;
- поведение при остановке, ошибке и частично успешной записи;
- что именно проверяют `verify_project.py`, `verify_capture_recovery.py`, `verify_save_safety.py`, `verify_recording_publication.py`;
- какие из этих проверок реально запускает `.github/workflows/validate.yml`.

### B. System diagnostics — BSOD Investigator

Проверить:

- как WinDbg/CDB output превращается в диагностическую модель;
- как отделяются сильные сигналы от слабых;
- как учитывается история независимых сбоев;
- почему повторный анализ одного dump не должен искусственно повышать уверенность;
- что проверяет безопасный `--self-test` в CI.

### C. Local AI — VoiceFlow

Проверить:

- аудио → faster-whisper pipeline;
- CPU/CUDA режимы;
- вставку стабильных фрагментов без финального дублирования;
- реакцию на смену активного окна;
- fallback-механизмы Windows input;
- какие части пока подтверждаются только syntax/compile CI и требуют реального Windows runtime для полного доказательства.

## Как читать проверки корректно

Наличие зелёного CI не означает, что аппаратно-зависимая функция полностью проверена. В портфолио используются разные уровни evidence:

1. **syntax/compile** — файл хотя бы корректно разбирается Python;
2. **unit/regression** — проверяется конкретный программный контракт без внешнего устройства;
3. **integration/self-test** — несколько компонентов проверяются вместе;
4. **runtime/manual Windows verification** — требуется реальное окно, audio device, GPU, WinAPI, FFmpeg или другое окружение.

При техническом просмотре важно смотреть, какой именно уровень доказывает конкретное утверждение.

## Сильные сигналы в проектах

### Поведение при ошибках

Интерес представляет не только happy path, но и поведение при зависшем дочернем процессе, сетевой ошибке, частично созданном результате, отмене пользователем, повторном запуске после сбоя и временно недоступном устройстве или внешнем инструменте.

### Проверяемость

В проектах используются GitHub Actions, `py_compile` / `compileall`, self-tests, regression tests, smoke tests и отдельные structural / publication / recovery проверки. Аппаратно-зависимые функции не считаются автоматически доказанными только потому, что прошёл compile step.

### Работа с пользовательскими данными

Стоит смотреть, что исключается из Git, как хранятся настройки, где используются backup/recovery, как ограничиваются логи/кэши и какие диагностические данные потенциально чувствительны.

### Поддерживаемость

В наиболее новых или переработанных проектах используются специализированные модули, `docs/`, `AGENTS.md`, явные entrypoints и проверки структуры. В legacy-модулях большой размер файла рассматривается как технический долг, а не как желательная архитектура.

## Повторяющийся инженерный принцип

```text
внешняя операция
    ↓
явное состояние / этап
    ↓
тайм-аут или ограниченный retry
    ↓
структурированная диагностика
    ↓
проверка результата
    ↓
безопасное восстановление или понятный failure state
```

## Дополнительная навигация

- [Главный профиль](README.md)
- [Карта проектов](PROJECTS.md)
- [Инженерный подход](ENGINEERING.md)
- [Поддержка и диагностика](SUPPORT.md)
