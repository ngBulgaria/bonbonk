FROM php:8.4-fpm

COPY --from=mlocati/php-extension-installer:latest /usr/bin/install-php-extensions /usr/local/bin/

RUN set -eux; \
    apt-get update; \
    apt-get install -y --no-install-recommends \
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
        redis; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html