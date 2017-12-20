FROM php:7.1-fpm

ADD sources.list    /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

Run docker-php-ext-install  mcrypt pdo_mysql opcache mysqli

RUN pecl install redis-3.1.4  swoole-1.9.23 &&\
    docker-php-ext-enable redis	swoole