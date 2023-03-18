FROM php:8.1.0-fpm-alpine

RUN docker-php-ext-install pdo_mysql bcmath

RUN apk --no-cache add pcre-dev ${PHPIZE_DEPS}
# RUN pecl install mongodb
# RUN docker-php-ext-enable mongodb
RUN pecl install redis
RUN docker-php-ext-enable redis
RUN apk del pcre-dev ${PHPIZE_DEPS}

RUN mkdir -p /var/www/html
WORKDIR /var/www/html
RUN chown -R www-data:www-data /var/www/html
USER www-data:www-data
