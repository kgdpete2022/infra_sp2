# api_yamdb project (v1)

#### Описание проекта

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории («Книги», «Фильмы», «Музыка»).

#### Используемые технологии

Django, DRF, PostgreSQL, Docker

#### Шаблон наполнения env-файла

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
DB_HOST=db
DB_PORT=5432
SECRET_KEY=secretkey
```

#### Запуск приложения в контейнерах

Для разворачивания проекта находясь в папке infra вызовете команду:

```
docker-compose up
```

Выполнить миграции:

```
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:

```
docker-compose exec web python manage.py createsuperuser
```

Собрать статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```

#### Заполнить базу данными

docker-compose exec web python manage.py loaddata fixtures.json

#### Примеры запросов API

Получение списка всех категорий:

```
GET /api/v1/categories/
```

Получение списка всех жанров

```
GET /api/v1/genres/
```

Получение списка всех произведений:

```
GET /api/v1/titles/
```

Получение информации о произведении:

```
GET /api/v1/titles/{titles_id}/
```

#### Разработчики

[Петр Шопин](https://github.com/kgdpete2022) - "тимлид", реализация review, comments

Дмитрий Алексеев - реализация categories, genres, titles

Дмитрий Кусков - реализация users
