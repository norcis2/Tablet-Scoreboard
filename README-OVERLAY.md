# YouTube Overlay — компактное табло и бегущая реклама

## Установка

Репозиторий: https://github.com/norcis2/Tablet-Scoreboard

Загрузите **три файла** из этого архива в корень репозитория: `overlay.html`, `sponsor-ticker.html`, `overlay-sponsors.json`. Подтвердите **Commit changes**. Они используют существующие `api-config.json`, `tournament.json` и папки `organizers/`, `sponsors/`. Планшетные `index.html`, `tablet.html`, `sponsors.json` не изменяйте.

## OBS Studio / Streamlabs

Создайте два **Browser Source** с размером **1920 × 1080** (внутри источника фон прозрачный):

1. **Scoreboard:** `https://norcis2.github.io/Tablet-Scoreboard/overlay.html?court=1`
2. **Sponsor Ticker:** `https://norcis2.github.io/Tablet-Scoreboard/sponsor-ticker.html`

Разместите оба источника поверх видео корта. Табло шириной около **600 px** располагается вверху по центру исходной области, рекламная полоса — вдоль нижней границы. Перемещать/масштабировать можно средствами OBS. Если нужно переместить табло в угол, используйте позиционирование и обрезку/трансформацию источника в OBS, либо измените CSS `#wrap`.

### Включить или отключить рекламу

- В OBS: щёлкните значок **глаза** у источника `Sponsor Ticker` (скрыть/показать).
- В ссылке: `sponsor-ticker.html?enabled=off` — реклама скрыта; без параметра — включена.
- В `overlay-sponsors.json`: `"generalSponsor": null, "partners": []` — блок полностью исчезает.

Рекламный источник не обращается к Rankedin и не влияет на счёт. `overlay.html` не отображает рекламу ни при каких настройках.

## Настройки спонсоров

`overlay-sponsors.json`:

```json
{
  "generalSponsor": "sponsors/Squashop.jpeg",
  "partners": [
    "sponsors/Pepsi centrs.jpg",
    "sponsors/Meste.jpg",
    "sponsors/Maxima.png"
  ],
  "speedPixelsPerSecond": 75,
  "heightPx": 78,
  "backgroundOpacity": 0.78
}
```

- `generalSponsor`: главный логотип, увеличенный относительно остальных. Для отключения — `null`.
- `partners`: логотипы в порядке движения. Можно оставить пустой массив.
- `speedPixelsPerSecond`: скорость движения справа налево (пикселей/сек), например 40 — медленно, 75 — обычно, 110 — быстро.
- `heightPx`: высота нижней полосы в пикселях, 40–140.
- `backgroundOpacity`: прозрачность фона от 0 (полностью прозрачный) до 0.98 (почти непрозрачный).

Логотипы загружаются из папки `sponsors/`. Имена файлов, пробелы и регистр должны точно совпадать. Форматы PNG, JPG, JPEG, SVG, WebP. Настройки автоматически перечитываются раз в 60 секунд; при изменении ссылки в OBS иногда требуется обновить источник.

## Корт и тестовый режим

Табло получает ID из `api-config.json` по номеру `?court=1` ... `?court=7`. Данные Rankedin обновляются каждые 5 секунд по текущей конфигурации.

Демо: `https://norcis2.github.io/Tablet-Scoreboard/overlay.html?court=1&demo=live`

Рекламная строка работает независимо от номера корта; один и тот же URL можно использовать во всех трансляциях.

## Если что-то не отображается

1. Убедитесь, что GitHub Pages публикуется из ветки `main`, папки `/ (root)`.
2. Убедитесь, что `overlay.html`, `sponsor-ticker.html` и `overlay-sponsors.json` находятся в корне репозитория.
3. Проверьте пути и точные имена файлов изображений.
4. Обновите Browser Source в OBS и проверьте URL в обычном Chrome.

## Важные замечания

Две страницы — два независимых Browser Source. Тикер работает в OBS как прозрачная веб-страница, но видимость/положение системных элементов OBS определяется настройками сцены. Не используйте эту версию как замену планшетному табло.
