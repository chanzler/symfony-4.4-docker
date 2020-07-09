FROM php:7.0.8-fpm-alpine

COPY wait-for-it.sh /usr/bin/wait-for-it

RUN chmod +x /usr/bin/wait-for-it

RUN apk --update --no-cache add git
RUN apk --update --no-cache add bash

RUN docker-php-ext-install pdo_mysql

RUN echo "memory_limit = -1" > /usr/local/etc/php/conf.d/memory.ini

COPY --from=composer /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

CMD composer install ; wait-for-it database:3306 -- bin/console doctrine:migrations:migrate ;  php-fpm 

EXPOSE 9000
