FROM php:apache

ARG DEBIAN_FRONTEND=noninteractive

ENV PHP_NAME_EXT=hello

RUN docker-php-source extract \
    && apt-get update && apt-get install -y --no-install-recommends nano \
    && cd /usr/src/php/ext && php ext_skel.php --ext $PHP_NAME_EXT

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini

WORKDIR /usr/src/php/ext/$PHP_NAME_EXT
