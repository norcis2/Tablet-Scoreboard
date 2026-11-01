SQUASH TABLET SCOREBOARD v15 — ANDROID GOOGLE CHROME

Upload ALL files and folders to the root of your GitHub Pages repository.

Open in Chrome:
  https://YOUR-USERNAME.github.io/YOUR-REPO/?court=1
  https://YOUR-USERNAME.github.io/YOUR-REPO/?court=2
  ... ?court=7

CONFIGURATION:
1. api-config.json — Rankedin API base URL, refresh interval, Rankedin court IDs for slots 1–7.
   Court 1 is configured with verified Rankedin ID 192806.
   Court 2–7 IDs are null: fill with actual Rankedin IDs when known.
   Unconfigured courts display COURT N / NOT CONFIGURED.
2. tournament.json — tournamentName and organizers logo paths (e.g. organizers/lsf.png).
3. sponsors.json — generalSponsor, partners, rotation timing.
   General sponsor appears alone first, then together with up to 3 partners per rotation.
4. Put organizer images into organizers/ and sponsor images into sponsors/.

Chrome on Android: use landscape orientation. The page uses available browser viewport
without scrolling, but standard Chrome address/system bars may remain visible.

The score refreshes every 5 seconds by default. Configuration files are reloaded
every 60 seconds. If the Rankedin API response format changes, JavaScript code
may require an update. Rankedin requests require browser-compatible CORS.

TEST MODES: ?court=1&demo=live or ?court=1&demo=next
DEBUG: ?court=1&debug=1

No PWA and no Kiosk Mode are included.

SQUASH TABLET SCOREBOARD v15 — ANDROID GOOGLE CHROME

Загрузите ВСЕ файлы и папки в корневой каталог вашего репозитория GitHub Pages.

Откройте в браузере Chrome:
https://YOUR-USERNAME.github.io/YOUR-REPO/?court=1
https://YOUR-USERNAME.github.io/YOUR-REPO/?court=2
... ?court=7

КОНФИГУРАЦИЯ:
1. api-config.json — базовый URL API Rankedin, интервал обновления, идентификаторы кортов (court ID) в системе Rankedin для слотов 1–7. 
Для корта 1 задан корректный ID Rankedin: 192806.
Для кортов 2–7 ID не указаны (null) — внесите актуальные идентификаторы Rankedin, как только они станут известны. 
Для не настроенных кортов отображается надпись: COURT N / NOT CONFIGURED.
2. tournament.json — название турнира (tournamentName) и пути к логотипам организаторов (например, organizers/lsf.png).
3. sponsors.json — генеральный спонсор, партнеры, параметры ротации. 
Сначала отображается только генеральный спонсор, затем — он же вместе с партнерами (до 3 партнеров за один цикл ротации).
4. Изображения организаторов разместите в папке organizers/, а изображения спонсоров — в папке sponsors/.

При использовании Chrome на Android установите альбомную (горизонтальную) ориентацию экрана. 
Страница адаптируется под доступную область просмотра браузера без необходимости прокрутки, 
однако стандартная адресная строка и системные элементы интерфейса Chrome могут оставаться видимыми.

По умолчанию счет обновляется каждые 5 секунд. Файлы конфигурации перезагружаются каждые 60 секунд. 
В случае изменения формата ответа API Rankedin может потребоваться обновление JavaScript-кода. 
Для выполнения запросов к API Rankedin необходима поддержка CORS (Cross-Origin Resource Sharing) на уровне браузера.

ТЕСТОВЫЕ РЕЖИМЫ: ?court=1&demo=live или ?court=1&demo=next
ОТЛАДКА (DEBUG): ?court=1&debug=1

Поддержка PWA и «киосковый режим» (Kiosk Mode) не предусмотрены.