ARG PHP_VERSION="7.4"
FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm-alpine

RUN apk update; \
    apk upgrade; \
    apk add composer;

RUN docker-php-ext-install pdo_mysql mbstring; \
    chown -R www-data:www-data /var/www/html