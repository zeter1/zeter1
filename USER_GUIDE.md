**Язык / Language:** **Русский** · [English](USER_GUIDE_EN.md)

# Выбор, скачивание и запуск

Выберите задачу в таблицах ниже. Название проекта ведёт к его коду и README; ссылка «Сборки» — к опубликованным Windows-файлам. Для технического знакомства с разработкой есть отдельный [маршрут по коду и проверкам](REVIEW_GUIDE.md).

## Браузерные приложения и игры

| Проект | Для чего | Как начать |
|---|---|---|
| [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) | Редактирование изображений, слои, выделение, рисование и эффекты | [Инструкция](https://github.com/zeter1/ZeTer-Photo-Editor#запуск-на-windows): скачать исходный ZIP, распаковать, открыть `start.bat` или `index.html`. Python и Node.js для обычного использования не нужны. |
| [BizPilot](https://github.com/zeter1/BizPilot) | Клиенты, задачи, сделки, доходы и расходы малого бизнеса | [Инструкция](https://github.com/zeter1/BizPilot#запуск): скачать исходный ZIP, распаковать, открыть `index.html` в современном браузере. |
| [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE) | Браузерный 3D-шутер с ботами | [Запуск и управление](https://github.com/zeter1/ZAP-ZONE#readme). Нужен современный настольный браузер с WebGL; требования к загрузке ресурсов указаны в README. |
| [CYBER RACE](https://github.com/zeter1/CYBER-RACE) | Гонки на вооружённых автомобилях | [Запуск и управление](https://github.com/zeter1/CYBER-RACE#запуск). Рекомендуется локальный HTTP-сервер; команда есть в README. |
| [Forest Hunter](https://github.com/zeter1/ForestHunter) | 3D-игра про охоту и выживание | [Запуск и управление](https://github.com/zeter1/ForestHunter#запуск). Рекомендуется локальный HTTP-сервер; команда есть в README. |

**Как скачать исходный ZIP:** откройте репозиторий → зелёная кнопка **Code** → **Download ZIP** → распакуйте всю папку. Для редактора и BizPilot не требуется сборка через npm. У игр свои требования к WebGL и сетевой загрузке библиотек; смотрите README выбранного проекта.

BizPilot хранит рабочее состояние в браузере. Сохраняйте ZIP-резервную копию через раздел «Ваши данные» перед очисткой хранилища или сменой браузера. В графическом редакторе сохраняйте рабочие проекты в файл: аварийное автосохранение не заменяет вашу копию.

## Windows-программы

Все перечисленные ниже опубликованные сборки сейчас отмечены **Pre-release**. Это предварительные версии для знакомства и тестирования; требования и известные ограничения определяет README конкретной программы.

| Задача | Программа и инструкция | Скачать |
|---|---|---|
| Записывать экран, звук и делать скриншоты | [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro#readme) | [Сборки](https://github.com/zeter1/Screen-Recorder-Pro/releases) |
| Надиктовывать текст в Windows-приложения | [VoiceFlow](https://github.com/zeter1/VoiceFlow#readme) | [Сборки](https://github.com/zeter1/VoiceFlow/releases) |
| Переводить и озвучивать видео | [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro#readme) | [Сборки](https://github.com/zeter1/Video-Translator-Pro/releases) |
| Скачивать видео и извлекать MP3 | [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader#readme) | [Сборки](https://github.com/zeter1/Universal-Video-Downloader/releases) |
| Превращать текст в озвучку и MP3 | [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows#readme) | [Сборки](https://github.com/zeter1/Text-to-MP3-Windows/releases) |
| Искать вакансии, убирать дубликаты и экспортировать Excel | [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro#readme) | [Сборки](https://github.com/zeter1/Vacancy-Parser-Pro/releases) |
| Исследовать причины синего экрана Windows | [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator#readme) | [Сборки](https://github.com/zeter1/BSOD-Investigator/releases) |
| Блокировать сеанс Windows с управлением переходом в сон | [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker#readme) | [Сборки](https://github.com/zeter1/Windows-PC-Locker/releases) |
| Вести заметки, задачи и локальное рабочее пространство | [ZeTer OS](https://github.com/zeter1/ZeTer-OS#readme) | [Сборки](https://github.com/zeter1/ZeTer-OS/releases) |

### Как скачать готовую программу

1. Перейдите по ссылке **Сборки** у выбранной программы и прочитайте описание выпуска.
2. В разделе **Assets** выберите файл программы `.exe` или архив Windows-сборки `.zip`. **Source code** — исходный код, а не готовая программа.
3. Архив распакуйте полностью; сохраните файлы рядом с исполняемым файлом. Следуйте README выбранной программы.
4. Если опубликован файл контрольной суммы SHA-256, используйте его для проверки целостности скачанного файла.

Готовая сборка и исходный код могут отличаться по версии. FFmpeg, модели распознавания речи, Windows-голоса, GPU-драйверы и доступ к внешним сервисам зависят от выбранного приложения. Наличие `.exe` само по себе не означает, что все эти компоненты включены. Запуск из исходников описан отдельно в README проекта.

## Видеоредактор в разработке

[Zeter Video Editor](https://github.com/zeter1/zeter-video-editor) — Windows-видеоредактор на Tauri, React, TypeScript, Rust и FFmpeg с многодорожечным монтажом и локальными проектами. Публичной готовой сборки в GitHub Releases пока нет. Начните с [README](https://github.com/zeter1/zeter-video-editor#readme) и [текущего статуса](https://github.com/zeter1/zeter-video-editor/blob/main/PROJECT_STATUS.md); инструкция для разработчиков относится к запуску из исходников.

## Если возникла проблема

Откройте **Issues** именно нужного проекта. Укажите версию, Windows или браузер, шаги, ожидаемый и фактический результат. Подготовьте небольшой пример без личных файлов и секретов; подробности — в [руководстве по сообщениям об ошибках](SUPPORT.md).

Связь с разработчиком: [https://t.me/zeter1](https://t.me/zeter1) · [zeter11@gmail.com](mailto:zeter11@gmail.com) · [https://www.facebook.com/zeter1](https://www.facebook.com/zeter1) · [https://vk.ru/zeter1](https://vk.ru/zeter1) · [https://www.instagram.com/zeter1992/](https://www.instagram.com/zeter1992/) · [https://tenchat.ru/zeter](https://tenchat.ru/zeter) · [https://x.com/zeter1](https://x.com/zeter1) · [https://www.threads.com/@zeter1992](https://www.threads.com/@zeter1992) · [https://ok.ru/zeter1](https://ok.ru/zeter1) · [https://t.me/zeterchat](https://t.me/zeterchat) — Telegram-группа: обо мне, проекты и чат. Для знакомства с архитектурой: [карта проектов](PROJECTS.md) · [инженерный подход](ENGINEERING.md).
