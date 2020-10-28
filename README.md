# YaMDB_final

Учебынй проект в рамках Яндекс.Практикума.
На YaMDb читатели оставляют к произведениям текстовые отзывы и выставляют рейтинг.

## Готовясь к запуску

Эти инструкции позволят вам запустить копию проекта на вашем локальном компьютере в целях разработки и тестирования.
Образ postgres [DockerHub](https://hub.docker.com/_/postgres).
Образ nginx [DockerHub](https://hub.docker.com/_/nginx).

## Требования

Перед запуском работы проверьте наличие 
[Python](https://www.python.org/downloads/),
[Django](https://www.djangoproject.com/), 
[Docker](https://www.docker.com/).

## Установка

*Клонируйте репозиторий на локальный компьютер. 
Выполните сборку контейнера.*
```
$ docker-compose build
```

*Запуск docker-compose.*
```
$ docker-compose up
```
При создании контейнера миграции выполнятся автоматически.

## Использование контейнера.

*Создание суперпользователя и инициализация данных.*

```sh
$ sudo docker exec -it <CONTAINER ID> python manage.py collectstatic
$ sudo docker exec -it <CONTAINER ID> python manage.py makemigrations
$ sudo docker exec -it <CONTAINER ID> python manage.py migrate
$ sudo docker exec -it <CONTAINER ID> python manage.py createsuperuser
$ sudo docker exec -it <CONTAINER ID> python manage.py loaddata fixtures.json
```
## Выключение контейнера.
```
docker-compose down
```
## Удаление контейнеров.
```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```

![yamdb_final workflow](https://github.com/smolyar741/yamdb_final/workflows/yamdb_final%20workflow/badge.svg)
![yamdb_final workflow](https://github.com/smolyar741/yamdb_final/workflows/yamdb_finalworkflow/badge.svg)

