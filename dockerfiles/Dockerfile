#  Dockerfile for Node Express Backend
FROM node:latest

RUN apt-get update; \
    apt-get upgrade -yqq; \
    apt-get install -yqq --no-install-recommends --show-progress \
          apt-utils \
          gnupg \
          gosu \
          git \
          curl \
          libcurl4-openssl-dev \
          ca-certificates \
          supervisor \
          libmemcached-dev \
          libz-dev \
          libbrotli-dev \
          libpq-dev \
          libjpeg-dev \
          libpng-dev \
          libfreetype6-dev \
          libssl-dev \
          libwebp-dev \
          libmcrypt-dev \
          libonig-dev \
          libzip-dev zip unzip \
          libargon2-1 \
          libidn2-0 \
          libpcre2-8-0 \
          libpcre3 \
          libxml2 \
          libzstd1 \
          procps

# Create App Directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY deployment/supervisord.conf /etc/supervisor/conf.d/supervisord.conf

COPY deployment/entrypoint.sh /
RUN chmod +x /entrypoint.sh

# Exports
EXPOSE 9000

ENTRYPOINT ["/entrypoint.sh"]
