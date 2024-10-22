FROM php:8.1-fpm

WORKDIR /vhapi

RUN apt-get update && apt-get install -y \
    libzip-dev \
    unzip \
    && docker-php-ext-install zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN docker-php-ext-install pdo pdo_mysql

CMD bash -c "composer install"


EXPOSE 9000

CMD ["php-fpm"]
