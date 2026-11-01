# Compact YouTube Overlay — обновление

Замените содержимое файла `overlay.html` в корне репозитория `norcis2/Tablet-Scoreboard` содержимым файла `overlay_compact.html` из архива (переименуйте в `overlay.html` перед загрузкой).

Изменено: максимальная ширина табло с 960 до 720 px; уменьшены столбцы геймов и очков, размеры шрифта и высота строк; блок спонсоров остаётся непосредственно под табло.

Не меняйте `index.html`, `tablet.html`, `api-config.json`, `tournament.json`, `sponsors.json`, `overlay-sponsors.json`.

Тест: https://norcis2.github.io/Tablet-Scoreboard/overlay.html?court=1&demo=live
Без спонсоров: добавьте `&sponsors=off`.
В OBS/Streamlabs Browser Source остаётся 1920×1080. Ширина самого табло будет не более 720 CSS-пикселей.
