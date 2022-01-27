FROM php:7.4.1-fpm-alpine

# COPY php.ini
COPY .docker/dev/api/php.ini /usr/local/etc/php/php.ini

# Composer install
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

RUN apk update && \
    apk add \
    git \
    zip \
    unzip \
    vim \
    autoconf gcc g++ make && \
    docker-php-ext-install pdo_mysql bcmath && \
    pecl install xdebug && \
    docker-php-ext-enable xdebug

WORKDIR /app
