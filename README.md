# API для Yatube

REST API для социальной сети Yatube.

## Возможности

- публикации постов
- комментарии к постам
- подписки на авторов
- группы
- JWT-аутентификация
- права доступа авторов

## Технологии

- Python
- Django
- Django REST Framework
- Simple JWT

## Установка

```bash
git clone <repo_url>
cd api-final-yatube-ad
python -m venv venv
source venv/Scripts/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
