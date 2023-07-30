
## Список ПО для разработки:
1. Python 3.11
2. Django
3. Docker
4. gunicorn
5. psycopg2-binary

## Список команд для запуска контейнера:

1. Сборка контейнера
`docker build -t perevyazko/dokerdjango:latest .`
2. Запуск контейнера
`docker run -p 8080:80 perevyazko/django-app`
3. Выгрузка контейнера на dockerhub
`docker push perevyazko/dokerdjango`
4.  Просмотр всех контейнеров
`docker ps -a`
5.  Удаление контейнера
`docker rm -f main_container`





