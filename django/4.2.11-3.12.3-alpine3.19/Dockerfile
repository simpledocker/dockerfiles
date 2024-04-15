FROM python:3.12.3-alpine3.19


LABEL org.opencontainers.image.title="Python, Django, DRF" \
      org.opencontainers.image.version="4.2.11-3.12.3-alpine3.19" \
      org.opencontainers.image.description="This image includes Python 3.12.3, Django 4.2.11, djangorestframework 3.15.1, psycopg2-binary 2.9.9, and other modules based on Alpine Linux 3.19. It is suitable for running Django applications that interact with PostgreSQL databases." \
      org.opencontainers.image.url="https://hub.docker.com/r/simpledocker/django" \
      org.opencontainers.image.source="https://github.com/simpledocker/dockerfiles" \
      org.opencontainers.image.vendor="SimpleDocker.com" \
      org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.authors="Simple Docker <dockerfiles@simpledocker.com>"

RUN apk add --no-cache postgresql-dev gcc python3-dev musl-dev \
    && apk cache clean \
    && python3 -m pip install \
    Django==4.2.11 \
    djangorestframework==3.15.1 \
    django-prometheus==2.3.1 \
    dj-database-url==2.1.0 \
    gunicorn==21.2.0 \
    redis==5.0.3 \
    psycopg2-binary==2.9.9
