FROM php:8-fpm

COPY php.ini /usr/local/etc/php/

RUN apt-get update \
  && apt-get install -y wget git unzip libpq-dev libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
  && docker-php-ext-install -j$(nproc) pdo_mysql opcache \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd

# composer
COPY --from=composer /usr/bin/composer /usr/bin/composer

# 環境変数
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME "/opt/composer"
ENV PATH "$PATH:/opt/composer/vendor/bin"

# Laravel
RUN composer global require laravel/installer

WORKDIR /app
