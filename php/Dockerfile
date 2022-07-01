FROM php:7.4.3-fpm

RUN docker-php-ext-install pdo_mysql

# 安裝 redis
RUN pecl install -o -f redis \
    &&  rm -rf /tmp/pear \
    &&  docker-php-ext-enable redis

RUN apt update && apt install --yes zip unzip

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer