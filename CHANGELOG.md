# История изменений

### 2026-10-22 — ZeTer Video Downloader в GitHub-профиле / Profile links refreshed

- Changed: название **ZeTer Video Downloader** и адрес `https://github.com/zeter1/ZeTer-Video-Downloader` синхронизированы в двуязычных README, каталогах проектов, руководствах, инженерном обзоре и поддержке. / Updated the application name and repository URL across the Russian and English profile documentation.
- Added: прямой переход к программе и её Windows Releases в быстрый выбор на главной странице профиля. / Added a direct application and Windows Releases entry to the top-level profile quick-selection tables.
- Fixed: ссылки на соответствующие русскую и английскую инструкции быстрого старта. / Corrected links to the language-specific quick-start sections.
- Verification: сравнение всех двенадцати обновляемых файлов с текущими SHA в `main`; проверка отсутствия устаревшего имени, URL и одинаковых целевых адресов в RU/EN. / Audited the twelve profile files for legacy names and URLs; checked matching RU/EN destinations.

Отслеживание изменений начинается с этой записи; более ранняя история не реконструировалась. Репозиторий документации не имеет номера версии продукта.

### 2026-10-11T22:19:08+03:00 — Ссылки на все сборки / Links to all builds

- Changed: в USER_GUIDE.md и USER_GUIDE_EN.md ссылки ZeTer Media Converter ведут на все сборки; убрана привязка к v3.3.5 в тексте и таблице. / Both user guides link all ZeTer Media Converter builds; version-specific references were removed from the text and table.
- Verification: проверены страница сборок, соответствие русской и английской правок, сохранность остальных строк таблиц и форматирование diff. / Checked the builds page, matching Russian and English edits, preservation of other table rows and diff formatting.

### 2026-10-11T15:47:35+03:00 — Результаты CI и обратная связь / CI results and feedback

- Changed: в обеих версиях профиля три инженерных примера связаны напрямую с результатами GitHub Actions; добавлена проверка соответствия ветки, commit и сборки. / Both profile versions link three engineering examples directly to GitHub Actions results and explain matching the branch, commit and build.
- Added: в обеих версиях поддержки — быстрые переходы, поиск похожих обращений и шаблон предложения функции. / Both support pages include section shortcuts, guidance for finding existing reports and a feature-request template.
- Changed: перед отчётом нужно сохранить версию, ошибку и важные данные; обновление или очистка настроек для обращения не требуются. / Reporting starts with recording the version and error and preserving important data; updating or clearing settings is not required to report a problem.
- Verification: проверены 12 публичных страниц, шесть языковых пар, 98 относительных файловых ссылок и 26 якорей; контакты, каталог и упоминания видеоредактора сохранены; новые страницы Actions доступны; git diff --check пройден. Репозитории приложений не менялись. / Checked 12 public pages, six language pairs, 98 relative file links and 26 anchors; contacts, catalog and video-editor references are preserved; new Actions destinations are accessible; git diff --check passed. Application repositories were not changed.

### 2026-10-11T15:27:21+03:00 — Проекты видны сразу / Projects visible by default

- Changed: полный список проектов в README.md и README_EN.md показан без раскрывающегося блока. / The full project list in README.md and README_EN.md is displayed without an expandable section.
- Verification: удалена только обёртка каталога в обеих версиях; текст, ссылки, переключатели языков и остальные раскрывающиеся блоки сохранены; git diff --check пройден. / Only the catalog wrapper was removed in both versions; text, links, language switches, and other expandable sections are preserved; git diff --check passed.

### 2026-10-11T15:22:51+03:00 — Компактный профиль и сквозная навигация / Compact profile and connected navigation

- Changed: в обеих версиях профиля полный каталог, ссылки на код и проверки и список технологий свёрнуты в раскрывающиеся блоки; выбор программы и три инженерных примера остаются открытыми. / Both profile versions place the full catalog, code and check links, and technology list in expandable sections; task selection and three engineering examples remain visible.
- Added: в начале десяти русских и английских страниц руководств — переходы к профилю, программам, техническому обзору и поддержке на выбранном языке. / Ten Russian and English guide pages now start with links to the profile, applications, technical review, and support in the selected language.
- Verification: проверены 12 страниц, 98 относительных файловых ссылок, шесть языковых пар, сохранность исходного текста и оформление diff. Репозитории приложений не менялись. / Checked 12 pages, 98 relative file links, six language pairs, original text preservation, and patch formatting. Application repositories were not changed.

### 2026-10-11T15:15:43+03:00 — Компактная связь и безопасное обновление / Focused contacts and safe updates

- Changed: в верхнем блоке обеих версий профиля оставлены Telegram и email; полный список контактов внизу сохранён. / The top contact block in both profile versions now contains Telegram and email; all footer contacts are preserved.
- Added: в обеих версиях пользовательского руководства — маршрут безопасного обновления Windows-программ: резервная копия, сохранение прежней сборки, проверка новой версии на тестовых данных и граница совместимости общего хранилища. / Both user guides now cover safe Windows-app updates: backups, keeping the previous build, trying the new version with test data, and shared-storage compatibility.
- Verification: проверены относительные ссылки, якоря, переключатели языков, сохранность контактов и разделов видеоредактора; проверка оформления diff пройдена. / Checked relative links, anchors, language switches, contact and video-editor section preservation; patch whitespace validation passed.

### 2026-10-11T15:05:24+03:00 — Удобный выбор и инженерные примеры / Navigation and engineering examples

- Changed: быстрые переходы и три инженерных примера с задачами, решениями и проверками в обеих версиях профиля. / Added quick navigation and three engineering examples connecting tasks, decisions and checks in both profile versions.
- Fixed: 16 ссылок из английского профиля и каталога ведут к английским инструкциям запуска. / Corrected 16 links from the English profile and catalog to English startup instructions.
- Added: прямые ZIP-ссылки для браузерных проектов, онлайн-запуск BizPilot и пример проверки SHA-256 Windows-сборки; русская и английская версии синхронизированы. / Added browser-project ZIP links, BizPilot online launch and a Windows-build SHA-256 example; Russian and English versions are aligned.
- Verification: проверены относительные ссылки и якоря, сохранность контактов и упоминаний видеоредактора; команда SHA-256 проверена на файле с известной суммой. / Checked relative links and anchors, preserved contacts and video-editor references; tested the SHA-256 command with a known-hash fixture.

### 2026-10-11T14:07:47+03:00 — Социальные сети и Telegram-группа / Social profiles and Telegram group

- Added: VK, Instagram, TenChat, X, Threads, OK и Telegram-группа во всех восьми контактных блоках русской и английской документации. / Added VK, Instagram, TenChat, X, Threads, OK, and the Telegram group to all eight contact blocks in both languages.
- Changed: группа обозначена как «обо мне, проекты и чат»; сохранены ранее опубликованные контакты, включая Facebook. Адреса всех контактов видны целиком. / The group is labelled as about me, projects and chat; existing contacts, including Facebook, are preserved. All contact URLs are displayed in full.
- Оформление: контакты показаны столбиком; ссылка на сообщение об ошибке вынесена в отдельный абзац.

### 2026-10-11T13:53:04+03:00 — Facebook в контактах / Facebook contact links

- Added: ссылка на Facebook во всех восьми контактных блоках README, пользовательского руководства и поддержки на русском и английском. / Added Facebook to all eight contact blocks in the Russian and English profile, user guide, and support pages.

### 2026-10-11T13:47:10+03:00 — Быстрый просмотр и поддержка / Quick review and support

- Changed: контакты и ссылка на поддержку доступны в начале русского и английского профиля. / Contact and support links are available near the top of both profile versions.
- Changed: технический маршрут на пять минут предлагает выбрать проект по направлению и сопоставить код с проверкой. / The five-minute review selects a project by role and connects code to checks.
- Added: готовый шаблон сообщения об ошибке и маршрут к Issues нужного проекта на русском и английском. / A copyable bug-report template and route to the relevant project's Issues in Russian and English.
- Verification: проверены внутренние ссылки, языковые переключатели, целевые пути в GitHub и Markdown-рендер шести страниц. / Checked relative links, language switches, target GitHub paths, and Markdown rendering for six pages.

### 2026-10-11T12:14:55+03:00 — Профиль для пользователей и технического просмотра

- Added: пользовательский каталог на русском и английском с выбором задачи, скачиванием и запуском.
- Changed: README профиля разделяет пользовательский и технический маршруты; карта проектов включает видеоредактор с точным статусом выпуска.
- Added: краткий AGENTS.md и каноническая карта владельцев документации.
- Changed: краткое описание профиля и репозитория отражает Python и Web; закреплены шесть приложений и веб-проектов.
