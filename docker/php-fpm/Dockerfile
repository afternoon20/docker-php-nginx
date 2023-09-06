FROM php:8.0.30-fpm

COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY php.ini /usr/local/etc/php/
RUN apt-get update && apt-get install -y \
    git \
    curl \
    zip \
    unzip \
    sudo \
  && apt install -y default-mysql-client \
  && docker-php-ext-install pdo_mysql
RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
RUN apt-get update
RUN sudo apt-get install -y nodejs

WORKDIR /var/www