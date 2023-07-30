
## Список ПО для разработки:
1. Python 3.11
2. Django
3. Docker
4. gunicorn
5. psycopg2-binary

## Список команд для запуска контейнера:
`Сборка контейнера`
1. docker build -t perevyazko/dokerdjango:latest .
`Запуск контейнера`
2. docker run -p 8080:80 perevyazko/django-app
`Выгрузка контейнера на dockerhub`
3. docker push perevyazko/dokerdjango
`Просмотр всех контейнеров`
4. docker ps -a
`Удаление контейнера`
5. docker rm -f main_container

