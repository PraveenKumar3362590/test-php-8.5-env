FROM php:8.5.12-apache

RUN apt-get update \
    && apt-get install -y --no-install-recommends git zip unzip libzip-dev \
    && docker-php-ext-install zip \
    && git config --system --add safe.directory '*' \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2.9.7 /usr/bin/composer /usr/bin/composer

RUN a2enmod rewrite