FROM python:3.12.3-slim-bookworm


LABEL org.opencontainers.image.title="Python, Django, DRF" \
      org.opencontainers.image.version="5.0.4-3.12.3-slim-bookworm" \
      org.opencontainers.image.description="This image includes Python 3.12.3, Django 5.0.4, djangorestframework 3.15.1, psycopg2-binary 2.9.9, and other modules based on Debian 12.5 Bookworm. It is suitable for running Django applications that interact with PostgreSQL databases." \
      org.opencontainers.image.url="https://hub.docker.com/r/simpledocker/django" \
      org.opencontainers.image.source="https://github.com/simpledocker/dockerfiles" \
      org.opencontainers.image.vendor="SimpleDocker.com" \
      org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.authors="Simple Docker <dockerfiles@simpledocker.com>"

RUN apt update \
    && apt install -y libpq-dev gcc python3-dev musl-dev \
    && apt clean \
    && python3 -m pip install \
    Django==5.0.4 \
    djangorestframework==3.15.1 \
    django-prometheus==2.3.1 \
    dj-database-url==2.1.0 \
    gunicorn==21.2.0 \
    redis==5.0.3 \
    psycopg2-binary==2.9.9
