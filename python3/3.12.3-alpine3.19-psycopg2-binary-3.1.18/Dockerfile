FROM python:3.12.3-alpine3.19


LABEL org.opencontainers.image.title="Python with psycopg2-binary" \
      org.opencontainers.image.version="3.12-alpine3.19-psycopg2-2.9.9" \
      org.opencontainers.image.description="This image provides Python 3.12 with Psycopg2 2.9.9, based on Alpine Linux 3.19. It is suitable for running Python applications that interact with PostgreSQL databases. Build-date: ${BUILD_DATE}." \
      org.opencontainers.image.url="https://hub.docker.com/simpledocker/python" \
      org.opencontainers.image.source="https://github.com/simpledocker/dockerfiles" \
      org.opencontainers.image.vendor="SimpleDocker.com" \
      org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.authors="Simple Docker <dockerfiles@simpledocker.com>"


# Install psycopg2
RUN apk add --no-cache postgresql-dev gcc python3-dev musl-dev \
    && pip install psycopg2==2.9.9
