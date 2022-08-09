FROM php:7.4.30-fpm-alpine3.16

RUN apk update
RUN apk add php-common php-intl php-mbstring php-xml icu-dev
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN docker-php-ext-configure intl && docker-php-ext-install intl
EXPOSE 9000 
