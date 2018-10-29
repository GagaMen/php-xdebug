FROM php:7.0-cli
MAINTAINER Felix Dimmel

RUN pecl install xdebug \
    && echo 'zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-20151012/xdebug.so' > \
        /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
    && php -m | grep xdebug