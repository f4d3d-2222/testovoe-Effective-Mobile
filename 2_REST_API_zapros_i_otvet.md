# API партнёрских магазинов для приложения "Петрушка Зеленая"

Документация REST API для экрана выбора магазина партнёра.

## Запрос

### Метод
`GET /api/v1/delivery/stores`

### Параметры (query)

| Параметр | Тип | Обязательный | Описание |
|----------|-----|--------------|----------|
| `address` | string | Да | Адрес доставки пользователя |
| `city`    | string | Нет | Город для уточнения зоны |

### Пример запроса
GET /api/v1/delivery/stores?address=ул.Ленина,д.10,кв.5&city=Москва
## Ответ

Формат: `JSON`

### Пример ответа
#### Описание полей ответа
| Поле | Тип | Описание |
|------|-----|----------|
| `id` | string | Уникальный идентификатор магазина |
| `name` | string | Название магазина |
| `logo_url` | string | Ссылка на логотип магазина |
| `delivery_info` | string | Строка с информацией о времени доставки |
| `external_url` | string | Ссылка для перехода на сайт партнёра |

```json
{
  "stores": [
    {
      "id": "metro_01",
      "name": "METRO",
      "logo_url": "https://cdn.petrushka-green.ru/partners/metro.png",
      "delivery_info": "Ближайшая доставка сегодня 21:00–23:00",
      "external_url": "https://www.metro-cc.ru/special/petrushka"
    },
    {
      "id": "auchan_01",
      "name": "Ашан",
      "logo_url": "https://cdn.petrushka-green.ru/partners/auchan.png",
      "delivery_info": "Ближайшая доставка сегодня 18:00–20:00",
      "external_url": "https://www.auchan.ru/promo/petrushka-green"
    },
    {
      "id": "vkusvill_01",
      "name": "ВкусВилл",
      "logo_url": "https://cdn.petrushka-green.ru/partners/vkusvill.png",
      "delivery_info": "Быстрая доставка от 20 до 60 минут",
      "external_url": "https://vkusvill.ru/actions/petrushka"
    },
    {
      "id": "victoria_01",
      "name": "ВИКТОРИЯ",
      "logo_url": "https://cdn.petrushka-green.ru/partners/victoria.png",
      "delivery_info": "Ближайшая доставка сегодня 17:00–19:00",
      "external_url": "https://www.victoria-group.ru/partner/petrushka"
    }
  ]
}
