# Yatube API

## Описание проекта

Yatube API — это RESTful API для социальной сети Yatube, которая позволяет пользователям создавать посты, комментировать их, подписываться на других пользователей и взаимодействовать с группами. API предоставляет возможность управлять контентом через HTTP-запросы, что делает его удобным для интеграции с мобильными приложениями, веб-сайтами и другими сервисами.

## Как запустить проект:

1. Клонировать репозиторий и перейти в него в командной строке:

   ```bash
   git clone https://github.com/At0mn1yIvan/api_final_yatube.git
   cd api_final_yatube
2. Cоздать и активировать виртуальное окружение:

   ```bash
   python3 -m venv env
   source env/bin/activate
3. Установить зависимости из файла requirements.txt:

   ```bash
   python3 -m pip install --upgrade pip
   pip install -r requirements.txt
4. Выполнить миграции:

   ```bash
   python manage.py migrate
5. Запустить проект:

   ```bash
   python manage.py runserver

## Примеры запросов к API

### Получение списка постов

- Запрос:

```bash
GET /api/v1/posts/
```
- Ответ:

```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```
### Создание нового поста

- Запрос:

```bash
POST /api/v1/posts/
```
- Тело запроса:

```json
{
  "text": "Новый пост",
  "image": "string",
  "group": 1
}
```
- Ответ:

```json
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2021-10-14T20:41:29.648Z",
  "image": "string",
  "group": 1
}
```
### Получение комментариев к посту

- Запрос:

```bash
GET /api/v1/posts/{post_id}/comments/
```
- Ответ:

```json
[
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "created": "2021-10-14T20:41:29.648Z",
    "post": 0
  }
]
```
### Подписка на пользователя

- Запрос:

```bash
POST /api/v1/follow/
```
- Тело запроса:

```json
{
  "following": "username"
}
```
- Ответ:

```json
{
  "user": "string",
  "following": "string"
}
```

## Документация к API

Полная документация API доступна по адресу http://127.0.0.1:8000/redoc/ после запуска проекта.
