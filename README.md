# Города и регионы России 2026 года

Датасет городов и регионов России в формате JSON. Основные источники — [Википедия](https://ru.wikipedia.org/) и данные Яндекс.Карт.

За дополнительными данными и услугами по сбору информации обращайтесь в Telegram: [https://t.me/webdillerru](https://t.me/webdillerru).

## Источники

- Википедия: [Список городов России](https://ru.wikipedia.org/wiki/Список_городов_России)
- Яндекс.Карты: идентификаторы, slug, координаты, число организаций

## Структура JSON

Корневой элемент — массив регионов. У региона есть список `cities`, инфобокс `regionInfo` и блок `yandexDetails`. У города — табличные поля, `cityInfo` и `yandexDetails`.

```json
{
  "data": [
    {
      "region": "Адыгея",
      "regionUrl": "https://ru.wikipedia.org/wiki/Адыгея",
      "id": 1,
      "slug": "adygeya",
      "cities": [
        {
          "id": 1,
          "slug": "1-adygeysk",
          "number": "7",
          "cityName": "Адыгейск",
          "cityUrl": "https://ru.wikipedia.org/wiki/Адыгейск",
          "gfz": "Адыгея",
          "regionUrl": "https://ru.wikipedia.org/wiki/Адыгея",
          "federalDistrict": "Южный",
          "population": 13175,
          "foundation": "1969",
          "cityStatus": "1976",
          "formerNames": "Адыгейский (до 1976);Теучежск (до 1990)",
          "coatOfArms": "https://upload.wikimedia.org/.../Coat_of_arms_of_Adygeysk.png",
          "cityInfo": {
            "cityName": "Адыгейск",
            "okato": "79403000000",
            "phoneCode": "+787772",
            "postalCode": "385 200",
            "density": 1053.86,
            "population": 13247,
            "timeZone": "UTC+3:00",
            "coordinates": { "lat": 44.884525, "lon": 39.19202 },
            "flagImage": "...",
            "coatOfArmsImage": "...",
            "gallery": [{ "alt": "...", "src": "..." }],
            "galleryCaption": "..."
          },
          "yandexDetails": {
            "yandexId": "11005",
            "yandexSlug": "adygeysk",
            "yandexCityName": "Адыгейск",
            "yandexLatitude": 44.884856,
            "yandexLongitude": 39.190567,
            "updatedAt": "2026-08-10T12:02:51.564Z"
          }
        }
      ],
      "regionInfo": {
        "regionName": "Республика Адыгея",
        "okato": "79",
        "phoneCode": "+7877",
        "density": 64.26,
        "population": 500731,
        "timeZone": "MSK (UTC+3)",
        "coordinates": { "lat": 44.65, "lon": 40 },
        "flagImage": "...",
        "coatOfArmsImage": "...",
        "gallery": [{ "alt": "", "src": "..." }],
        "galleryCaption": ""
      },
      "yandexDetails": {
        "yandexId": "11004",
        "yandexSlug": "republic-of-adygea",
        "yandexRegionName": "Республика Адыгея",
        "yandexLatitude": 44.884856,
        "yandexLongitude": 39.190567,
        "updatedAt": "2026-08-10T12:02:51.564Z"
      }
    }
  ]
}
```

### Поля региона

| Поле | Тип | Описание |
|------|-----|----------|
| `region` | string | Название субъекта РФ |
| `regionUrl` | string | Страница региона в Википедии |
| `id` | number | Внутренний ID региона |
| `slug` | string | URL-slug региона |
| `cities` | array | Список городов региона |
| `regionInfo` | object | Инфобокс региона из Википедии |
| `yandexDetails` | object | Данные региона с Яндекс.Карт |

### Поля города (таблица списка)

| Поле | Тип | Описание |
|------|-----|----------|
| `id` | number | Внутренний ID города |
| `slug` | string | URL-slug города |
| `number` | string | Порядковый номер в списке Википедии |
| `cityName` | string | Название города |
| `cityUrl` | string | Страница города в Википедии |
| `coatOfArms` | string \| null | Миниатюра герба (из таблицы) |
| `gfz` | string | Субъект РФ (как в таблице) |
| `regionUrl` | string | Страница региона в Википедии |
| `federalDistrict` | string | Федеральный округ |
| `population` | number \| null | Население (из таблицы) |
| `foundation` | string \| null | Год основания / первого упоминания |
| `cityStatus` | string \| null | Год получения статуса города |
| `formerNames` | string \| null | Прежние названия |
| `cityInfo` | object \| null | Инфобокс города из Википедии |
| `yandexDetails` | object \| null | Данные города с Яндекс.Карт |

### `cityInfo` / `regionInfo`

| Поле | Тип | Описание |
|------|-----|----------|
| `cityName` / `regionName` | string | Официальное название из инфобокса |
| `region` | string | Название региона |
| `cityUrl` / `regionUrl` | string | Ссылка на Википедию |
| `okato` | string | Код ОКАТО |
| `phoneCode` | string | Телефонный код |
| `postalCode` | string | Почтовый индекс |
| `density` | number \| null | Плотность населения |
| `population` | number \| null | Население из инфобокса |
| `timeZone` | string | Часовой пояс |
| `coordinates.lat` | number | Широта (Википедия) |
| `coordinates.lon` | number | Долгота (Википедия) |
| `flagImage` | string \| null | URL флага |
| `coatOfArmsImage` | string \| null | URL герба |
| `gallery` | array | Галерея `{ alt, src }` |
| `galleryCaption` | string | Подпись к галерее |

### `yandexDetails`

| Поле | Тип | Описание |
|------|-----|----------|
| `yandexId` | string | ID сущности на Яндекс.Картах |
| `yandexSlug` | string | Slug в URL карт |
| `yandexCityName` / `yandexRegionName` | string | Название с карточки Яндекс |
| `yandexLatitude` | number | Широта (Яндекс) |
| `yandexLongitude` | number | Долгота (Яндекс) |
| `updatedAt` | string | Время обновления (ISO) |

> Координаты и население в таблице, `cityInfo`/`regionInfo` и `yandexDetails` могут отличаться — это разные источники.

---

# Cities and Regions of Russia 2026 year

A JSON dataset of Russian cities and regions. Primary sources are [Wikipedia](https://en.wikipedia.org/) and Yandex Maps.


For additional data and information collection services, contact me on Telegram: [https://t.me/webdillerru](https://t.me/webdillerru).

## Sources

- Wikipedia: [List of cities and towns in Russia](https://en.wikipedia.org/wiki/List_of_cities_and_towns_in_Russia)
- Yandex Maps: IDs, slugs, coordinates

## JSON structure

The root value is an array of regions. Each region has a `cities` list, a Wikipedia `regionInfo` object, and a `yandexDetails` block. Each city has table fields, `cityInfo`, and `yandexDetails`.

See the example in the Russian section above.

### Region fields

| Field | Type | Description |
|-------|------|-------------|
| `region` | string | Federal subject name |
| `regionUrl` | string | Wikipedia page URL for the region |
| `id` | number | Internal region ID |
| `slug` | string | Region URL slug |
| `cities` | array | Cities in this region |
| `regionInfo` | object | Wikipedia infobox for the region |
| `yandexDetails` | object | Yandex Maps data for the region |

### City fields (list table)

| Field | Type | Description |
|-------|------|-------------|
| `id` | number | Internal city ID |
| `slug` | string | City URL slug |
| `number` | string | Ordinal number in the Wikipedia list |
| `cityName` | string | City name |
| `cityUrl` | string | Wikipedia page URL for the city |
| `coatOfArms` | string \| null | Coat of arms thumbnail (from the table) |
| `gfz` | string | Federal subject (as in the table) |
| `regionUrl` | string | Wikipedia page URL for the region |
| `federalDistrict` | string | Federal district |
| `population` | number \| null | Population (from the table) |
| `foundation` | string \| null | Foundation / first mention year |
| `cityStatus` | string \| null | Year city status was granted |
| `formerNames` | string \| null | Previous names |
| `cityInfo` | object \| null | Wikipedia infobox for the city |
| `yandexDetails` | object \| null | Yandex Maps data for the city |

### `cityInfo` / `regionInfo`

| Field | Type | Description |
|-------|------|-------------|
| `cityName` / `regionName` | string | Official name from the infobox |
| `region` | string | Region name |
| `cityUrl` / `regionUrl` | string | Wikipedia URL |
| `okato` | string | OKATO code |
| `phoneCode` | string | Phone area code |
| `postalCode` | string | Postal code |
| `density` | number \| null | Population density |
| `population` | number \| null | Population from the infobox |
| `timeZone` | string | Time zone |
| `coordinates.lat` | number | Latitude (Wikipedia) |
| `coordinates.lon` | number | Longitude (Wikipedia) |
| `flagImage` | string \| null | Flag image URL |
| `coatOfArmsImage` | string \| null | Coat of arms image URL |
| `gallery` | array | Gallery items `{ alt, src }` |
| `galleryCaption` | string | Gallery caption |

### `yandexDetails`

| Field | Type | Description |
|-------|------|-------------|
| `yandexId` | string | Yandex Maps entity ID |
| `yandexSlug` | string | Slug in Maps URLs |
| `yandexCityName` / `yandexRegionName` | string | Name from the Yandex card |
| `yandexLatitude` | number | Latitude (Yandex) |
| `yandexLongitude` | number | Longitude (Yandex) |
| `updatedAt` | string | Last update time (ISO) |

> Values for coordinates and population may differ across the table, `cityInfo`/`regionInfo`, and `yandexDetails` because they come from different sources.
