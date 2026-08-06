# Cities and Regions of Russia
#### English / Английский
A dataset of cities and regions of Russia, sourced from open data, primarily [Wikipedia](https://en.wikipedia.org/). The data is provided in JSON format for easy integration into various projects.

## Data Source
- **Wikipedia**: [List of cities and towns in Russia](https://en.wikipedia.org/wiki/List_of_cities_and_towns_in_Russia_by_population)
- **Data License**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)

## Data Structure
The `cities_regions.json` file contains a list of objects with the following structure (example):
```json
"data": [
    {
      "region": "Хакасия",
      "regionUrl": "https://ru.wikipedia.org/wiki/Хакасия",
      "cities": [
        {
          "number": "1",
          "coatOfArms": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Coat_of_Arms_of_Abaza_%28Khakassia%29.png/40px-Coat_of_Arms_of_Abaza_%28Khakassia%29.png?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
          "cityName": "Абаза",
          "cityUrl": "https://ru.wikipedia.org/wiki/Абаза_(город)",
          "gfz": "Хакасия",
          "regionUrl": "https://ru.wikipedia.org/wiki/Хакасия",
          "federalDistrict": "Сибирский",
          "population": 12272,
          "foundation": "1867",
          "cityStatus": "1966",
          "formerNames": "Абаканский Завод, Абаканско-Заводское",
          "cityInfo": {
            "cityUrl": "https://ru.wikipedia.org/wiki/Абаза_(город)",
            "regionUrl": "https://ru.wikipedia.org/wiki/Хакасия",
            "cityName": "Абаза",
            "region": "Хакасия",
            "phoneCode": "+739047",
            "postalCode": "655750",
            "okato": "95402000000",
            "density": 150.57,
            "population": 11823,
            "timeZone": "UTC+7:00",
            "coordinates": {
              "lat": 52.65,
              "lon": 90.083333333333
            },
            "flagImage": "https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Flag_of_Abaza.png/250px-Flag_of_Abaza.png?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
            "coatOfArmsImage": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Coat_of_Arms_of_Abaza_%28Khakassia%29.png/120px-Coat_of_Arms_of_Abaza_%28Khakassia%29.png?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
            "gallery": [
              {
                "src": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/01/%D0%93%D0%BE%D1%80%D0%BE%D0%B4_%D0%90%D0%B1%D0%B0%D0%B7%D0%B0.jpg/330px-%D0%93%D0%BE%D1%80%D0%BE%D0%B4_%D0%90%D0%B1%D0%B0%D0%B7%D0%B0.jpg?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
                "alt": ""
              }
            ],
            "galleryCaption": ""
          }
        }
        ...
      ]
    }
    ...
]
```

### Field Descriptions

| Field | Type | Description |
|-------|------|-------------|
| **`data`** | `array` | A list of region objects. |
| **Region object** | | |
| `region` | `string` | Name of the federal subject (region, republic, krai, etc.). |
| `regionUrl` | `string` | URL to the Wikipedia page of the region. |
| `cities` | `array` | List of city objects belonging to this region. |
| **City object** | | |
| `number` | `string` | Ordinal number of the city in the list (e.g., "1"). |
| `coatOfArms` | `string` | URL to a thumbnail (40px) of the city's coat of arms. |
| `cityName` | `string` | Name of the city. |
| `cityUrl` | `string` | URL to the Wikipedia page of the city. |
| `gfz` | `string` | Federal subject (same as region, often used for classification). |
| `regionUrl` | `string` | (Duplicate) URL to the region's Wikipedia page. |
| `federalDistrict` | `string` | Federal district of Russia (e.g., "Сибирский"). |
| `population` | `number` | Population of the city (source: Wikipedia). |
| `foundation` | `string` | Year (or date) the city was founded. |
| `cityStatus` | `string` | Year when the settlement was granted city status. |
| `formerNames` | `string` | Previous names of the city (comma‑separated). |
| `cityInfo` | `object` | Additional detailed information about the city. |
| **CityInfo object** | | |
| `cityUrl` | `string` | (Duplicate) URL to city's Wikipedia page. |
| `regionUrl` | `string` | (Duplicate) URL to region's Wikipedia page. |
| `cityName` | `string` | (Duplicate) City name. |
| `region` | `string` | (Duplicate) Region name. |
| `phoneCode` | `string` | Telephone dialing code (with `+`). |
| `postalCode` | `string` | Postal code. |
| `okato` | `string` | OKATO code (Russian administrative classification). |
| `density` | `number` | Population density (people per km²). |
| `population` | `number` | (Duplicate) Population value (may differ slightly from the main field). |
| `timeZone` | `string` | Time zone (e.g., `UTC+7:00`). |
| `coordinates` | `object` | Geographic coordinates. |
| `coordinates.lat` | `number` | Latitude (decimal). |
| `coordinates.lon` | `number` | Longitude (decimal). |
| `flagImage` | `string` | URL to the city's flag image (250px). |
| `coatOfArmsImage` | `string` | URL to the city's coat of arms image (120px). |
| `gallery` | `array` | Array of image objects for the city gallery. |
| `gallery[].src` | `string` | URL to the gallery image. |
| `gallery[].alt` | `string` | Alt text for the image (may be empty). |
| `galleryCaption` | `string` | Caption for the gallery (often empty). |

> **Note:** Some fields are duplicated (e.g., `population`, `regionUrl`) – they come directly from the parsed Wikipedia infobox and may contain slightly different values.

# Города и регионы России
#### Russian / Русский
Данные о городах и регионах России, полученные из открытых источников, в первую очередь — из [Википедии](https://ru.wikipedia.org/). Данные представлены в формате JSON для удобства использования в различных проектах.

## Источник данных
- **Википедия**: [Список городов России](https://ru.wikipedia.org/wiki/Список_городов_России)
- **Лицензия данных**: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)

## Структура данных
Файл `cities_regions.json` содержит список объектов со следующей структурой (пример):
```json
"data": [
    {
      "region": "Хакасия",
      "regionUrl": "https://ru.wikipedia.org/wiki/Хакасия",
      "cities": [
        {
          "number": "1",
          "coatOfArms": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Coat_of_Arms_of_Abaza_%28Khakassia%29.png/40px-Coat_of_Arms_of_Abaza_%28Khakassia%29.png?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
          "cityName": "Абаза",
          "cityUrl": "https://ru.wikipedia.org/wiki/Абаза_(город)",
          "gfz": "Хакасия",
          "regionUrl": "https://ru.wikipedia.org/wiki/Хакасия",
          "federalDistrict": "Сибирский",
          "population": 12272,
          "foundation": "1867",
          "cityStatus": "1966",
          "formerNames": "Абаканский Завод, Абаканско-Заводское",
          "cityInfo": {
            "cityUrl": "https://ru.wikipedia.org/wiki/Абаза_(город)",
            "regionUrl": "https://ru.wikipedia.org/wiki/Хакасия",
            "cityName": "Абаза",
            "region": "Хакасия",
            "phoneCode": "+739047",
            "postalCode": "655750",
            "okato": "95402000000",
            "density": 150.57,
            "population": 11823,
            "timeZone": "UTC+7:00",
            "coordinates": {
              "lat": 52.65,
              "lon": 90.083333333333
            },
            "flagImage": "https://upload.wikimedia.org/wikipedia/commons/thumb/d/db/Flag_of_Abaza.png/250px-Flag_of_Abaza.png?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
            "coatOfArmsImage": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Coat_of_Arms_of_Abaza_%28Khakassia%29.png/120px-Coat_of_Arms_of_Abaza_%28Khakassia%29.png?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
            "gallery": [
              {
                "src": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/01/%D0%93%D0%BE%D1%80%D0%BE%D0%B4_%D0%90%D0%B1%D0%B0%D0%B7%D0%B0.jpg/330px-%D0%93%D0%BE%D1%80%D0%BE%D0%B4_%D0%90%D0%B1%D0%B0%D0%B7%D0%B0.jpg?utm_source=ru.wikipedia.org&utm_campaign=parser&utm_content=thumbnail",
                "alt": ""
              }
            ],
            "galleryCaption": ""
          }
        }
        ...
      ]
    }
    ...
]
```
### Описание полей

| Поле | Тип | Описание |
|------|-----|----------|
| **`data`** | `массив` | Список объектов регионов. |
| **Объект региона** | | |
| `region` | `строка` | Название субъекта федерации (республика, край, область и т.д.). |
| `regionUrl` | `строка` | Ссылка на страницу региона в Википедии. |
| `cities` | `массив` | Список объектов городов, принадлежащих этому региону. |
| **Объект города** | | |
| `number` | `строка` | Порядковый номер города в списке (например, «1»). |
| `coatOfArms` | `строка` | Ссылка на миниатюру (40px) герба города. |
| `cityName` | `строка` | Название города. |
| `cityUrl` | `строка` | Ссылка на страницу города в Википедии. |
| `gfz` | `строка` | Субъект федерации (обычно совпадает с `region`, используется для классификации). |
| `regionUrl` | `строка` | (Дубликат) Ссылка на страницу региона. |
| `federalDistrict` | `строка` | Федеральный округ России (например, «Сибирский»). |
| `population` | `число` | Население города (по данным Википедии). |
| `foundation` | `строка` | Год (или дата) основания города. |
| `cityStatus` | `строка` | Год получения статуса города. |
| `formerNames` | `строка` | Прежние названия города (через запятую). |
| `cityInfo` | `объект` | Дополнительная подробная информация о городе. |
| **Объект CityInfo** | | |
| `cityUrl` | `строка` | (Дубликат) Ссылка на страницу города. |
| `regionUrl` | `строка` | (Дубликат) Ссылка на страницу региона. |
| `cityName` | `строка` | (Дубликат) Название города. |
| `region` | `строка` | (Дубликат) Название региона. |
| `phoneCode` | `строка` | Телефонный код (с «+»). |
| `postalCode` | `строка` | Почтовый индекс. |
| `okato` | `строка` | Код ОКАТО (общероссийский классификатор). |
| `density` | `число` | Плотность населения (чел./км²). |
| `population` | `число` | (Дубликат) Значение населения (может незначительно отличаться от основного поля). |
| `timeZone` | `строка` | Часовой пояс (например, `UTC+7:00`). |
| `coordinates` | `объект` | Географические координаты. |
| `coordinates.lat` | `число` | Широта (в десятичных градусах). |
| `coordinates.lon` | `число` | Долгота (в десятичных градусах). |
| `flagImage` | `строка` | Ссылка на изображение флага города (250px). |
| `coatOfArmsImage` | `строка` | Ссылка на изображение герба города (120px). |
| `gallery` | `массив` | Массив объектов изображений для галереи города. |
| `gallery[].src` | `строка` | Ссылка на изображение в галерее. |
| `gallery[].alt` | `строка` | Альтернативный текст для изображения (может быть пустым). |
| `galleryCaption` | `строка` | Подпись для галереи (часто пустая). |

> **Примечание:** Некоторые поля дублируются (например, `population`, `regionUrl`) – они взяты непосредственно из парсинга инфобокса Википедии и могут содержать немного разные значения.
