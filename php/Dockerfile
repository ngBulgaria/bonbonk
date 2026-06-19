FROM php:8.3-fpm-alpine

WORKDIR /var/www/html

RUN apk add --no-cache \
    bash \
    curl \
    git \
    icu-dev \
    libzip-dev \
    oniguruma-dev \
    unzip \
    zip \
    $PHPIZE_DEPS \
  && docker-php-ext-install \
    intl \
    mbstring \
    opcache \
    pdo \
    pdo_mysql \
    zip \
  && pecl install redis \
  && docker-php-ext-enable redis

COPY php/php.ini /usr/local/etc/php/conf.d/bonbonk.ini