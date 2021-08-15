FROM php:7.3.27-fpm

WORKDIR /var/app

RUN docker-php-ext-install pdo pdo_mysql mysqli && docker-php-ext-enable mysqli


# CMD ["php", "-S", "0.0.0.0:7000"]