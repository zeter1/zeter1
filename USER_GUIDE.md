**Язык / Language:** **Русский** · [English](USER_GUIDE_EN.md)

[Профиль](README.md) · **Программы** · [Технический обзор](REVIEW_GUIDE.md) · [Поддержка](SUPPORT.md)

# Выбор, скачивание и запуск

Выберите задачу в таблицах ниже. Название проекта ведёт к его коду и README; ссылка «Сборки» — к опубликованным Windows-файлам. Для технического знакомства с разработкой есть отдельный [маршрут по коду и проверкам](REVIEW_GUIDE.md).

Быстрый переход: [браузерные приложения и игры](#браузерные-приложения-и-игры) · [Windows-программы](#windows-программы) · [проверка скачанного файла](#как-проверить-скачанный-файл) · [безопасное обновление](#как-безопасно-обновить-windows-программу) · [сообщить о проблеме](#если-возникла-проблема).

## Браузерные приложения и игры

| Проект | Для чего | Как начать |
|---|---|---|
| [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) | Редактирование изображений, слои, выделение, рисование и эффекты | [Скачать ZIP](https://github.com/zeter1/ZeTer-Photo-Editor/archive/refs/heads/main.zip) · [Инструкция](https://github.com/zeter1/ZeTer-Photo-Editor#запуск-на-windows). Распаковать, открыть `start.bat` или `index.html`. Python и Node.js для обычного использования не нужны. |
| [BizPilot](https://github.com/zeter1/BizPilot) | Клиенты, задачи, сделки, доходы и расходы малого бизнеса | [Запустить онлайн](https://dkl.do.am/portfolio/bizpilot/index.html) · [Скачать ZIP](https://github.com/zeter1/BizPilot/archive/refs/heads/main.zip) · [Инструкция](https://github.com/zeter1/BizPilot#запуск). Локально: распаковать, открыть `index.html` в современном браузере. |
| [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE) | Браузерный 3D-шутер с ботами | [Скачать ZIP](https://github.com/zeter1/ZAP-ZONE/archive/refs/heads/main.zip) · [Запуск и управление](https://github.com/zeter1/ZAP-ZONE#readme). Нужен современный настольный браузер с WebGL; требования к загрузке ресурсов указаны в README. |
| [CYBER RACE](https://github.com/zeter1/CYBER-RACE) | Гонки на вооружённых автомобилях | [Скачать ZIP](https://github.com/zeter1/CYBER-RACE/archive/refs/heads/main.zip) · [Запуск и управление](https://github.com/zeter1/CYBER-RACE#запуск). Рекомендуется локальный HTTP-сервер; команда есть в README. |
| [Forest Hunter](https://github.com/zeter1/ForestHunter) | 3D-игра про охоту и выживание | [Скачать ZIP](https://github.com/zeter1/ForestHunter/archive/refs/heads/main.zip) · [Запуск и управление](https://github.com/zeter1/ForestHunter#запуск). Рекомендуется локальный HTTP-сервер; команда есть в README. |

**Как скачать исходный ZIP:** откройте репозиторий → зелёная кнопка **Code** → **Download ZIP** → распакуйте всю папку. Для редактора и BizPilot не требуется сборка через npm. У игр свои требования к WebGL и сетевой загрузке библиотек; смотрите README выбранного проекта.

BizPilot хранит рабочее состояние в браузере. Сохраняйте ZIP-резервную копию через раздел «Ваши данные» перед очисткой хранилища или сменой браузера. Онлайн-версия и локальная копия не синхронизируются: для переноса используйте ZIP-экспорт и импорт. В графическом редакторе сохраняйте рабочие проекты в файл: аварийное автосохранение не заменяет вашу копию.

## Windows-программы

Статус выпуска зависит от проекта: сборки могут быть обычными релизами или иметь пометку **Pre-release**. Актуальную версию и статус проверяйте на странице сборок; требования и известные ограничения определяет README конкретной программы.

| Задача | Программа и инструкция | Скачать |
|---|---|---|
| Записывать экран, звук и делать скриншоты | [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro#readme) | [Сборки](https://github.com/zeter1/Screen-Recorder-Pro/releases) |
| Надиктовывать текст в Windows-приложения | [VoiceFlow](https://github.com/zeter1/VoiceFlow#readme) | [Сборки](https://github.com/zeter1/VoiceFlow/releases) |
| Переводить и озвучивать видео | [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro#readme) | [Сборки](https://github.com/zeter1/Video-Translator-Pro/releases) |
| Скачивать видео и извлекать MP3 | [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader#readme) | [Сборки](https://github.com/zeter1/Universal-Video-Downloader/releases) |
| Преобразовывать видеокурсы в MP3 и объединять видео | [ZeTer Media Converter](https://github.com/zeter1/ZeTer-Media-Converter) | [Все сборки](https://github.com/zeter1/ZeTer-Media-Converter/releases) |
| Превращать текст в озвучку и MP3 | [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows#readme) | [Сборки](https://github.com/zeter1/Text-to-MP3-Windows/releases) |
| Искать вакансии, убирать дубликаты и экспортировать Excel | [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro#readme) | [Сборки](https://github.com/zeter1/Vacancy-Parser-Pro/releases) |
| Исследовать причины синего экрана Windows | [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator#readme) | [Сборки](https://github.com/zeter1/BSOD-Investigator/releases) |
| Блокировать сеанс Windows с управлением переходом в сон | [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker#readme) | [Сборки](https://github.com/zeter1/Windows-PC-Locker/releases) |
| Вести заметки, задачи и локальное рабочее пространство | [ZeTer OS](https://github.com/zeter1/ZeTer-OS#readme) | [Сборки](https://github.com/zeter1/ZeTer-OS/releases) |

**ZeTer Media Converter:** Windows 10/11 x64, автономный EXE со встроенными Python, FFmpeg и FFprobe. Программа не подписана Authenticode. Скачивайте с [официальной страницы сборок](https://github.com/zeter1/ZeTer-Media-Converter/releases) и проверяйте контрольную сумму SHA-256.

### Как скачать готовую программу

1. Перейдите по ссылке **Сборки** у выбранной программы и прочитайте описание выпуска.
2. В разделе **Assets** выберите файл программы `.exe` или архив Windows-сборки `.zip`. **Source code** — исходный код, а не готовая программа.
3. Архив распакуйте полностью; сохраните файлы рядом с исполняемым файлом. Следуйте README выбранной программы.
4. Если опубликован файл контрольной суммы SHA-256, используйте его для проверки целостности скачанного файла.

Готовая сборка и исходный код могут отличаться по версии. FFmpeg, модели распознавания речи, Windows-голоса, GPU-драйверы и доступ к внешним сервисам зависят от выбранного приложения. Наличие `.exe` само по себе не означает, что все эти компоненты включены. Запуск из исходников описан отдельно в README проекта.

### Как проверить скачанный файл

Пример для Screen Recorder Pro, у которого опубликованы EXE и контрольная сумма:

1. Скачайте `Screen-Recorder-Pro.exe` и `Screen-Recorder-Pro.sha256.txt` из **одного и того же выпуска** в [Releases](https://github.com/zeter1/Screen-Recorder-Pro/releases).
2. Откройте PowerShell в папке с этими файлами и выполните:

```powershell
Get-FileHash -LiteralPath '.\Screen-Recorder-Pro.exe' -Algorithm SHA256
```

3. Сравните значение **Hash** с SHA-256 в скачанном `.sha256.txt`: все 64 символа должны совпасть, регистр букв не важен. При несовпадении не запускайте этот файл; скачайте его заново из того же выпуска.

Команда читает файл и не запускает программу. Совпадение подтверждает соответствие опубликованной контрольной сумме; оно не заменяет проверку источника загрузки или цифровую подпись. Для другой программы используйте её имя файла и контрольную сумму из того же выпуска.

## Как безопасно обновить Windows-программу

1. Прочитайте описание нового выпуска и README программы: там указаны изменения, требования и порядок переноса данных.
2. Завершите текущие операции, сохраните результат и сделайте резервную копию важных данных средствами программы. Полностью закройте приложение перед копированием файлов.
3. Сохраните прежнюю сборку. Если README допускает запуск из распакованной папки, распакуйте новую версию в отдельную папку; для установщика следуйте инструкции проекта.
4. Проверьте контрольную сумму, если она опубликована, и испытайте новую версию на копии или небольшом тестовом файле. Проверьте открытие, основную операцию и сохранение результата.
5. Переносите рабочие данные только способом, описанным в README. Если новая версия не подходит, закройте её и возвращайтесь к прежней сборке с резервной копией данных, созданной до обновления.

Отдельная папка программы не гарантирует отдельное хранилище: версии могут использовать общие настройки или базу данных. Совместимость данных новой версии со старой должна быть подтверждена документацией проекта. Если порядок переноса не описан, [уточните его у разработчика](SUPPORT.md), прежде чем открывать единственную копию важных данных.

## Видеоредактор в разработке

[Zeter Video Editor](https://github.com/zeter1/zeter-video-editor) — Windows-видеоредактор на Tauri, React, TypeScript, Rust и FFmpeg с многодорожечным монтажом и локальными проектами. Публичной готовой сборки в GitHub Releases пока нет. Начните с [README](https://github.com/zeter1/zeter-video-editor#readme) и [текущего статуса](https://github.com/zeter1/zeter-video-editor/blob/main/PROJECT_STATUS.md); инструкция для разработчиков относится к запуску из исходников.

## Если возникла проблема

Откройте **Issues** именно нужного проекта. Укажите версию, Windows или браузер, шаги, ожидаемый и фактический результат. Подготовьте небольшой пример без личных файлов и секретов; подробности — в [руководстве по сообщениям об ошибках](SUPPORT.md).

Связь с разработчиком:

- [https://t.me/zeter1](https://t.me/zeter1)
- [zeter11@gmail.com](mailto:zeter11@gmail.com)
- [https://www.facebook.com/zeter1](https://www.facebook.com/zeter1)
- [https://vk.ru/zeter1](https://vk.ru/zeter1)
- [https://www.instagram.com/zeter1992/](https://www.instagram.com/zeter1992/)
- [https://tenchat.ru/zeter](https://tenchat.ru/zeter)
- [https://x.com/zeter1](https://x.com/zeter1)
- [https://www.threads.com/@zeter1992](https://www.threads.com/@zeter1992)
- [https://ok.ru/zeter1](https://ok.ru/zeter1)
- [https://t.me/zeterchat](https://t.me/zeterchat) — Telegram-группа: обо мне, проекты и чат

Для знакомства с архитектурой: [карта проектов](PROJECTS.md) · [инженерный подход](ENGINEERING.md).
