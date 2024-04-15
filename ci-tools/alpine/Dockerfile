FROM alpine:3.19.1


LABEL org.opencontainers.image.title="CD/CI Tools (git, curl, aws, ansible, terraform, etc)" \
      org.opencontainers.image.version="alpine3.19-20240416" \
      org.opencontainers.image.description="" \
      org.opencontainers.image.url="https://hub.docker.com/simpledocker/ci-tools" \
      org.opencontainers.image.source="https://github.com/simpledocker/dockerfiles" \
      org.opencontainers.image.vendor="SimpleDocker.com" \
      org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.authors="Simple Docker <dockerfiles@simpledocker.com>"

# Installing other tools
RUN apk add \
    git \
    curl \
    make \
    rsync \
    aws-cli \
    ansible \
    && apk cache clean

ENV PRODUCT="terraform"
ENV VERSION="1.7.2"

# Installing terraform
RUN apk add --update --virtual .deps --no-cache gnupg && \
    cd /tmp && \
    wget https://releases.hashicorp.com/${PRODUCT}/${VERSION}/${PRODUCT}_${VERSION}_linux_amd64.zip && \
    wget https://releases.hashicorp.com/${PRODUCT}/${VERSION}/${PRODUCT}_${VERSION}_SHA256SUMS && \
    wget https://releases.hashicorp.com/${PRODUCT}/${VERSION}/${PRODUCT}_${VERSION}_SHA256SUMS.sig && \
    wget -qO- https://www.hashicorp.com/.well-known/pgp-key.txt | gpg --import && \
    gpg --verify ${PRODUCT}_${VERSION}_SHA256SUMS.sig ${PRODUCT}_${VERSION}_SHA256SUMS && \
    grep ${PRODUCT}_${VERSION}_linux_amd64.zip ${PRODUCT}_${VERSION}_SHA256SUMS | sha256sum -c && \
    unzip /tmp/${PRODUCT}_${VERSION}_linux_amd64.zip -d /tmp && \
    mv /tmp/${PRODUCT} /usr/local/bin/${PRODUCT} && \
    rm -f /tmp/${PRODUCT}_${VERSION}_linux_amd64.zip ${PRODUCT}_${VERSION}_SHA256SUMS ${VERSION}/${PRODUCT}_${VERSION}_SHA256SUMS.sig && \
    apk del .deps \
