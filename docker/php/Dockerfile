FROM php:8.4-fpm-alpine

WORKDIR /var/www/html

COPY --from=mlocati/php-extension-installer:latest /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions \
    intl \
    mbstring \
    opcache \
    pdo_mysql \
    redis \
    zip

COPY docker/php/conf.d/*.ini /usr/local/etc/php/conf.d/

COPY public/ /var/www/html/

CMD ["php-fpm"]