FROM php:8.4-fpm-alpine

COPY --from=mlocati/php-extension-installer:latest /usr/bin/install-php-extensions /usr/local/bin/

RUN set -eux; \
    apk add --no-cache \
        bash \
        curl \
        git \
        unzip \
        zip; \
    install-php-extensions \
        intl \
        mbstring \
        opcache \
        pdo_mysql \
        zip \
        redis

WORKDIR /var/www/html