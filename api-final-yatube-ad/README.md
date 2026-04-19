# API для Yatube

REST API для социальной платформы **Yatube**. Проект позволяет работать с публикациями, комментариями, сообществами и подписками через HTTP API.

## Что умеет API

- получать список публикаций и отдельные публикации;
- создавать, редактировать и удалять свои посты;
- просматривать и добавлять комментарии к публикациям;
- получать список сообществ;
- подписываться на авторов и искать подписки;
- получать JWT-токены для аутентификации.

Неаутентифицированным пользователям доступно только чтение, кроме эндпоинта подписок `/api/v1/follow/`, который доступен только после авторизации.

## Технологии

- Python
- Django
- Django REST Framework
- Simple JWT
- SQLite

## Как запустить проект локально

```bash
git clone <repo_url>
cd api-final-yatube-ad/yatube_api
python -m venv venv
source venv/bin/activate      # Linux/macOS
# venv\Scripts\activate       # Windows
pip install -r ../requirements.txt
python manage.py migrate
python manage.py runserver
```

Документация Redoc будет доступна по адресу:

```text
http://127.0.0.1:8000/redoc/
```

## Примеры запросов

### Получить JWT-токен

```http
POST /api/v1/jwt/create/
Content-Type: application/json

{
  "username": "TestUser",
  "password": "1234567"
}
```

### Создать пост

```http
POST /api/v1/posts/
Authorization: Bearer <access_token>
Content-Type: application/json

{
  "text": "Мой первый пост",
  "group": 1
}
```

### Подписаться на автора

```http
POST /api/v1/follow/
Authorization: Bearer <access_token>
Content-Type: application/json

{
  "following": "username"
}
```
