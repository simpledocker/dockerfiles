FROM debian:bookworm-slim

LABEL org.opencontainers.image.title="CD/CI Tools (git, curl, aws, ansible, terraform, etc)" \
      org.opencontainers.image.version="noble-20240225-20240416" \
      org.opencontainers.image.description="" \
      org.opencontainers.image.url="https://hub.docker.com/simpledocker/ci-tools" \
      org.opencontainers.image.source="https://github.com/simpledocker/dockerfiles" \
      org.opencontainers.image.vendor="SimpleDocker.com" \
      org.opencontainers.image.licenses="MIT" \
      org.opencontainers.image.authors="Simple Docker <dockerfiles@simpledocker.com>"


RUN apt update \
    && apt install -y \
    git \
    curl \
    make \
    rsync \
    ansible \
    unzip \
    # Terraform \
    && apt install -y gnupg software-properties-common wget \
    && wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg \
    && echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/hashicorp.list \
    && apt update \
    && apt install -y terraform \
    ## AWS CLI \
    && curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf aws awscliv2.zip \
    && aws --version \
    && apt-get clean \
