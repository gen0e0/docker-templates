FROM php:7.4-fpm

WORKDIR /backend

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    # for japanese env
    locales-all \
    # for composer
    git unzip \
    # for php extension gd
    zlib1g-dev \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    # for php extension zip
    libzip-dev \
    # for php extension imagick
    libmagickwand-dev --no-install-recommends \
    # for processing pdf by imagick
    ghostscript

# install java environment for tabula
RUN mkdir -p /usr/share/man/man1 && apt-get install -y default-jre

RUN apt-get clean && rm -r /var/lib/apt/lists/*

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8

# install imagick
RUN pecl install imagick
COPY ./infra/docker/php/policy.xml /etc/ImageMagick-6/policy.xml

RUN docker-php-ext-install pdo_mysql && \
    docker-php-ext-install zip && \
    docker-php-ext-install gd && \
    docker-php-ext-enable imagick

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_NO_INTERACTION 1
ENV COMPOSER_HOME /composer
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

COPY ./backend .
RUN composer install --no-interaction
