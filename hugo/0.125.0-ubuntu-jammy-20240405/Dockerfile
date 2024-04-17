FROM simpledocker/ci-tools AS builder
RUN wget https://github.com/gohugoio/hugo/releases/download/v0.125.0/hugo_0.125.0_linux-amd64.deb

FROM ubuntu:jammy-20240405
COPY --from=builder hugo_0.125.0_linux-amd64.deb .
RUN apt update \
    && apt install -y git \
    && dpkg -i hugo_0.125.0_linux-amd64.deb \
    && rm hugo_0.125.0_linux-amd64.deb \
    && apt-get clean \
    && rm -rf /var/cache/apt/list \
    && mkdir /src

WORKDIR /src
ENTRYPOINT hugo
