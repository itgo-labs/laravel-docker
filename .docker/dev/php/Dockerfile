FROM php:8.1-fpm-alpine3.18

# Install system dependencies
RUN apk update && apk add --update --no-cache git \
    curl \
    libpng-dev \
    libxml2-dev \
    zip \
    unzip \
    vim \
    sudo \
    libzip-dev \
    zip \
    npm \
    bash

RUN docker-php-ext-install pdo_mysql #mbstring exif pcntl bcmath gd zip

# Clear cache
RUN rm -rf /var/cache/apk/*

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN chown -R www-data:www-data /var/www
WORKDIR /var/www


