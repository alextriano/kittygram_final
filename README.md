![GitHub Workflow Status (with event)](https://img.shields.io/github/actions/workflow/status/alextriano/kittygram_final/Add%20fix16)

# Kittygram

## О проекте

В данном сервисе реализована соцсеть для владельцев кошек, в которой можно делиться фото котов и их достижениями.

## Технологии

Python 3.9, Django 4.1, Django REST framework, React, Docker, Nginx.

## Запуск проекта на локальном компьютере

Клонировать репозиторий и перейти в него в командной строке:
```bash
git clone https://github.com/alextriano/kittygram_final.git
cd kittygram_final
```
Создать файл .evn для хранения ключей:
```bash
SECRET_KEY='указать секретный ключ'
ALLOWED_HOSTS='указать имя или IP хоста'
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
DEBUG=False
```
Запустить docker-compose.production:
```bash
docker compose -f docker-compose.production.yml up
```
Выполнить миграции, сбор статики:
```bash
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
```
Создать суперпользователя, ввести почту, логин, пароль:
```bash
docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser
```
# Автор проекта
[Александр Волков](https://github.com/alextriano)