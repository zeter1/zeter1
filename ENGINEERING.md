**Язык / Language:** **Русский** · [English](ENGINEERING_EN.md)

# Инженерный подход

Этот документ дополняет профиль и показывает практики, которые применяются в моих **Python** и **Web** проектах. Цель — не использовать одинаковый шаблон везде, а выбирать проверяемые решения под реальный риск проекта.

## 1. Диагностика должна помогать найти первопричину

Большой сырой лог сам по себе редко решает проблему. В сложных проектах диагностика должна сохранять этап операции, входные параметры, traceback или код ошибки, состояние внешнего компонента и итоговую сводку.

Примеры:
- **BSOD Investigator** объединяет crash dump, WinDbg/CDB, Event Log, метаданные драйверов и историю прошлых сбоев.
- **Screen Recorder Pro** отдельно диагностирует FFmpeg-команды, тайминги, аудиоустройства, плавность записи и lifecycle процессов.
- **Vacancy Parser Pro** разделяет проблемы по внешним источникам.
- В браузерных проектах ошибки runtime/rendering не должны теряться между UI, игровым циклом и Web API.

## 2. Длительная операция не должна быть «чёрным ящиком»

Для операций, идущих минуты или часы, нужен явный прогресс, корректная отмена и возможность сохранить выполненную работу.

Используемые подходы:
- checkpoints и recovery;
- heartbeat для долгих процессов;
- bounded retry вместо бесконечных повторов;
- timeouts и return-code validation;
- повторное использование промежуточных артефактов;
- безопасная очистка временных данных.

**Video Translator Pro** показывает этот подход на длинном Whisper → translation → TTS → FFmpeg pipeline.

## 3. Успешная команда ещё не означает успешный результат

Где возможно, проверяется конечный артефакт или observable behavior:
- готовое видео — через FFprobe;
- downloader — через проверку результата после download/remux/transcoding;
- browser runtime — smoke-тестом фактической инициализации до явного ready-marker, а не только HTTP-доступности;
- графические форматы — regression tests на import/export contracts;
- критичные сценарии — безопасными self-tests.

Практический пример: **BizPilot** прошёл syntax/local-asset checks, но первый настоящий headless Chrome smoke остановился на `cashflowForecast is not defined`. Ошибка была классифицирована как реальная runtime-регрессия, а не проблема CI; после этого cash-flow logic вынесена в тестируемый модуль, добавлены regression tests и boot-stage diagnostics, и новый browser smoke стал зелёным.

## 4. Внешняя зависимость должна иметь границы отказа

API, сайт, драйвер, FFmpeg, CDN, WebGL context или аудиоустройство могут отказать независимо от приложения.

Поэтому нужны:
- изоляция интеграций;
- локальная обработка ошибок;
- fallback только там, где он корректен;
- bounded retry;
- явное завершение дочерних процессов;
- диагностический контекст конкретной зависимости.

В web-проектах к этому добавляются CDN fallback, WebGL context recovery и graceful degradation качества.

## 5. Состояние браузерного приложения — часть архитектуры

Local-first приложение должно явно определять:
- что хранится в `localStorage`, IndexedDB или памяти;
- что считается пользовательскими данными;
- как выполняются backup/restore;
- как переживается crash/reload;
- какие данные можно безопасно удалить;
- что никогда не должно попадать в Git.

**BizPilot** использует локальное состояние и ZIP backup/restore. **ZeTer Photo Editor** использует IndexedDB для аварийного восстановления несохранённых документов.

## 6. Rendering и realtime-код требуют бюджетов

В Canvas/WebGL-проектах корректность недостаточна: важны frame budget, память и количество realtime-объектов.

Подходы:
- `requestAnimationFrame`;
- object pools;
- `InstancedMesh`;
- spatial grids;
- ограничение тяжёлых операций;
- bounded caches;
- adaptive quality;
- typed pixel pipelines там, где Canvas8 недостаточен.

Это видно в **ZeTer Photo Editor**, **ZAP ZONE**, **CYBER RACE** и **Forest Hunter**.

## 7. Большой файл — сигнал проверить границы ответственности

По мере роста проекта код разделяется, если это уменьшает связанность и упрощает изменения.

Примеры:
- **Screen Recorder Pro** разделяет UI, capture, audio, FFmpeg, process management и diagnostics.
- **ZeTer OS** использует модульный JavaScript frontend и отдельный Python/native bridge.
- **ZAP ZONE** разделяет engine, weapons, player state, combat, entities, progression и runtime.
- **CYBER RACE** и **Forest Hunter** переведены с giant inline runtime на staged subsystem boundaries (`core/game/ai/weapons/audio/ui`) без одномоментного rewrite; architecture docs и structural validators фиксируют эти границы.
- **BizPilot** выделяет cash-flow engine из UI orchestration, чтобы финансовую математику можно было проверять отдельно от DOM.
- **Universal Video Downloader** содержит code map и инструменты определения минимального scope изменения.

## 8. Проверка должна соответствовать реальному риску

Используется комбинация:
- syntax / compile checks;
- unit и regression tests;
- self-tests;
- structural checks;
- structural architecture checks;
- headless browser boot smoke с explicit ready-marker;
- GitHub Actions;
- ручная runtime-проверка там, где нужны реальная Windows-сессия, GPU, аудиоустройство или интерактивный браузер.

Зелёный CI не считается доказательством того, что аппаратно-зависимая функция полностью проверена.

## 9. Пользовательские данные требуют отдельной стратегии

Настройки, runtime-state, кэши, crash recovery, diagnostic artifacts и пользовательские документы не должны случайно смешиваться с исходниками.

В зависимости от проекта используются:
- локальное хранение вне репозитория;
- backup/restore;
- crash autosave;
- bounded logs/caches;
- sanitization диагностических данных;
- явные правила `.gitignore`.

## 10. AI-assisted development требует тех же проверок, что и обычная разработка

ChatGPT и Codex используются для analysis, refactoring, debugging и реализации. Изменение не считается корректным только потому, что выглядит правдоподобно.

Для больших проектов используются architecture docs, code maps, `AGENTS.md`, tests, CI и diagnostics, чтобы уменьшить scope изменений и риск регрессий.

## Репозитории по направлениям

**Web:** [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) · [BizPilot](https://github.com/zeter1/BizPilot) · [ZAP ZONE](https://github.com/zeter1/ZAP-ZONE) · [CYBER RACE](https://github.com/zeter1/CYBER-RACE) · [Forest Hunter](https://github.com/zeter1/ForestHunter)

**Python / Windows:** [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro) · [BSOD Investigator](https://github.com/zeter1/BSOD-Investigator) · [VoiceFlow](https://github.com/zeter1/VoiceFlow) · [Video Translator Pro](https://github.com/zeter1/Video-Translator-Pro) · [Vacancy Parser Pro](https://github.com/zeter1/Vacancy-Parser-Pro) · [Universal Video Downloader](https://github.com/zeter1/Universal-Video-Downloader) · [Text to MP3 for Windows](https://github.com/zeter1/Text-to-MP3-Windows) · [Windows PC Locker](https://github.com/zeter1/Windows-PC-Locker)

**Hybrid:** [ZeTer OS](https://github.com/zeter1/ZeTer-OS)
