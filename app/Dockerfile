# Используем базовый образ Python
FROM python:3.11

ENV POSTGRES_DB djangoDB
ENV POSTGRES_USER postgres
ENV POSTGRES_PASSWORD parolDjango!

RUN apt-get update \
    && apt-get install -y postgresql postgresql-contrib

RUN service postgresql start \
    && su - postgres -c "psql -c \"ALTER USER postgres WITH PASSWORD '$POSTGRES_PASSWORD';\""

RUN service postgresql start \
    && su - postgres -c "createdb $POSTGRES_DB"

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
WORKDIR /app
COPY requirements.txt .


RUN pip install --upgrade pip
RUN pip install --trusted-host pypi.python.org -r requirements.txt

COPY .. /app

RUN service postgresql start && python manage.py migrate && \
    echo "from django.contrib.auth import get_user_model; User = get_user_model();  \
    User.objects.create_superuser('admin', 'admin@example.com', 'password')" | python manage.py shell


EXPOSE 8000

CMD service postgresql start && gunicorn app.wsgi:application --bind 0.0.0.0:8000

