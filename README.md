# YaMDb

[Описание](#описание) /

[История изменений](#история-изменений) /

[Запуск в Docker](#запуск-в-docker) /

[Документация](#документация)


## Описание
Проект [YaMDb](https://github.com/slavspart/infra_sp2) собирает отзывы пользователей на произведения. В этом репозитории бэкенд проекта (приложение reviews) и API для него (приложение api), разработанные командой авторов:

* <a href="https://github.com/slavspart" target="_blank">slavspart</a>
* <a href="https://github.com/oitczvovich" target="_blank">oitczvovich</a>
* <a href="https://github.com/avtorsky" target="_blank">avtorsky</a>

## История_изменений
Release 20220729:
- feat(./):приложение переработано для работы с NGINX, Postgresql и подготовлено для контейнеризации при помощи Docker

Release 20220706:
* fix(./api_yamdb/api/): поправлен линтинг в сериализаторах, вьюсеты CategoryViewSet и GenreViewSet переписаны согласно принципу DRY 
* fix(./api_yamdb/api_yamdb/): минорные изменения в конфиге settings.py
* fix(./api_yamdb/reviews/models.py): внесены правки в модели Comment и Review

Release 20220704:
* fix(./api_yamdb/): внесены правки в приложения api и reviews по результатам code reivew

Release 20220630:
* feat(./api_yamdb/api/filters.py): поддержана кастомная логика фильтрации объектов для эндпойнта api/v1/titles/
* fix(./api_yamdb/api/): выполнена отладка компонентов приложения api по unit-тестам

Release 20220628:
* feat(./api_yamdb/api/): подготовлены вьюсеты и сериализаторы моделей Category, Comment, Genre, Review, Title, User
* feat(./api_yamdb/api/urls.py): настроен роутинг для всех эндпойнтов API

Release 20220623:
* feat(./api_yamdb/reviews/models.py): подготовлены модели Category, Comment, Genre, GenreTitle, Review, Title, User
* feat(./api_yamdb/reviews/migrations): выполнены миграции
* build: разрешены конфликты в git, результаты командной работы влиты в ветку dev/sprint-10

Release 20220620:
* docs(./README.md): настройка git, определение ролей в команде

## Запуск в Docker

```bash
git clone https://github.com/slavspart/infra_sp2.git
cd infra/
```

Создать локально файл окружения .env, в который записать SECRET_KEY, HOSTS, DB_ENGINE,DB_NAME, POSTGRES_USER, POSTGRES_PASSWORD, DB_HOST, DB_PORT далее продолжить:

```bash
docker-compose up -d --build
docker-compose exec web python manage.py migrate
```

## Документация

```bash
python3 manage.py runserver
http://localhost/redoc/
```
