**Язык / Language:** **Русский** · [English](PROJECTS_EN.md)

# Карта проектов

Этот файл — расширенная навигация по опубликованным проектам. Главный README даёт краткий обзор, а здесь проекты сгруппированы по инженерным направлениям и по тому, что именно в них полезно смотреть.

## Windows и системная интеграция

### [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator)

**Задача:** расследование причин BSOD в Windows на основе crash dumps, Windows Event Log, метаданных драйверов и истории предыдущих сбоев.

**Что смотреть:**

- интеграцию с Microsoft CDB / WinDbg;
- модель оценки подозреваемых драйверов по нескольким источникам доказательств;
- различие между силой доказательств и качеством телеметрии;
- SQLite-историю, fingerprint сбоев и защиту от повторного учёта одного падения;
- self-test и CI;
- работу с UAC, защищёнными системными файлами и диагностическими пакетами.

**Инженерный акцент:** диагностика первопричин, осторожная работа с неопределённостью и сохранение контекста для повторного анализа.

---

### [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)

**Задача:** безопасно блокировать Windows и при необходимости не позволять системе перейти в сон, пока выполняются фоновые задачи.

**Что смотреть:**

- `LockWorkStation`, `SetThreadExecutionState`, WTS API;
- single-instance защита через mutex;
- lifecycle режима предотвращения сна;
- безопасный self-test;
- компактное логирование с ограничением размера и срока хранения.

**Инженерный акцент:** WinAPI через `ctypes`, системное состояние и аккуратное поведение фоновой утилиты.

---

### [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows)

**Задача:** чтение текста системными голосами Windows и создание MP3 из больших текстов.

**Что смотреть:**

- Microsoft SAPI и COM;
- глобальные горячие клавиши;
- сохранение состояния нескольких вкладок;
- восстановление длинных заданий конвертации;
- интеграцию с FFmpeg и Windows-аудио.

**Инженерный акцент:** Windows desktop, state persistence и восстановление длительных операций.

## Мультимедиа

### [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro)

**Задача:** запись экрана, микрофона и системного звука, создание скриншотов и работа с аннотациями.

**Что смотреть:**

- FFmpeg Desktop Duplication (`ddagrab`);
- GPU pipeline и NVIDIA NVENC;
- CoreAudio loopback fallback;
- управление дочерними процессами FFmpeg;
- модульную структуру `screen_recorder/`;
- отдельные проверяющие скрипты для capture recovery, save safety и publication flow;
- диагностические данные таймингов и плавности записи.

**Инженерный акцент:** real-time multimedia, process management, fallback-стратегии и регрессионная защита сложного desktop-приложения.

---

### [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro)

**Задача:** распознать речь в видео, перевести её, синтезировать новую озвучку и собрать итоговый ролик.

**Что смотреть:**

- Whisper → translation → TTS → FFmpeg pipeline;
- Pause Sync для длинных переведённых реплик;
- checkpoint/recovery;
- persistent TTS cache;
- ограниченные retry и защита от каскада сетевых ошибок;
- финальную валидацию готового MP4.

**Инженерный акцент:** длинные многоэтапные workflow, восстановление после сбоев и проверка конечного результата, а не только успешного завершения процесса.

---

### [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader)

**Задача:** получить удобный MP4 до 1080p либо MP3 с сайтов, поддерживаемых yt-dlp.

**Что смотреть:**

- выбор форматов yt-dlp;
- стратегию `compatible streams → lossless remux → transcoding fallback`;
- проверку результата через ffprobe;
- модульную структуру;
- `docs/CODE_MAP.md` и инструменты определения минимальной области кода для изменений.

**Инженерный акцент:** совместимость медиа, минимизация лишнего перекодирования и поддерживаемость проекта.

## Speech / AI

### [VoiceFlow](https://github.com/zeter1/VoiceFlow)

**Задача:** локальный голосовой ввод текста прямо в активное поле любого Windows-приложения.

**Что смотреть:**

- faster-whisper;
- CPU/CUDA execution paths;
- потоковую обработку стабильных фрагментов речи;
- переключение между активными окнами во время диктовки;
- нативную вставку текста и fallback-механизмы;
- разделённую диагностику hotkeys / capture / inference / insertion;
- privacy-first модель: распознавание локально после загрузки модели.

**Инженерный акцент:** real-time pipeline, локальный ML inference, Windows input automation и конкурентные фоновые задачи.

## Гибридные desktop/web-приложения

### [ZeTer OS](https://github.com/zeter1/ZeTer-OS)

**Задача:** локальное рабочее пространство, объединяющее заметки, задачи, календарь, файлы, таблицы и другие инструменты.

**Что смотреть:**

- Python desktop shell + pywebview;
- native bridge между Python и JavaScript;
- модульный frontend;
- local-first state model;
- резервные копии и точки восстановления;
- portable release pipeline;
- структурные проверки и JavaScript smoke-тесты.

**Инженерный акцент:** границы между frontend/native слоями, управление пользовательскими данными и архитектура растущего приложения.

## Сеть, парсинг и данные

### [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro)

**Задача:** собирать вакансии из нескольких источников, фильтровать, дедуплицировать и экспортировать результаты.

**Что смотреть:**

- отдельные адаптеры источников;
- изоляцию ошибок одного сайта от общей поисковой сессии;
- локальную фильтрацию и дедупликацию;
- экспорт в Excel;
- структурированные диагностические сессии;
- offline regression tests парсерной логики.

**Инженерный акцент:** нестабильные внешние источники, fault isolation и наблюдаемость сетевого workflow.

## Как смотреть портфолио

Если времени мало:

1. Начать с [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) — самый широкий набор Windows/multimedia задач.
2. Посмотреть [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator) — системная диагностика и работа с доказательствами.
3. Открыть [VoiceFlow](https://github.com/zeter1/VoiceFlow) — локальный AI и real-time speech pipeline.
4. Посмотреть [ZeTer OS](https://github.com/zeter1/ZeTer-OS) — гибридная Python/JavaScript архитектура.
5. Для надёжности длительных workflow — [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro).

Дополнительно: [ENGINEERING.md](ENGINEERING.md) описывает общие инженерные принципы, повторяющиеся в этих проектах.