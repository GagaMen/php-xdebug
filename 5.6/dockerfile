FROM php:5.6-cli
MAINTAINER Felix Dimmel

RUN pecl install xdebug-2.5.5 \
    && echo 'zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-20131226/xdebug.so' > \
        /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \
    && php -m | grep xdebug