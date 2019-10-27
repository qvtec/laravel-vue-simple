FROM php:7.3.4-apache

COPY ./php/php.ini /usr/local/etc/php/
COPY ./apache/*.conf /etc/apache2/sites-enabled/

RUN apt-get update && \
    apt-get install -y apt-utils mysql-client && \
    docker-php-ext-install mysqli mbstring pdo pdo_mysql && \
    a2enmod rewrite

# php7.3からlibzipのインストールが必要
RUN apt-get install -yqq libzip-dev zip unzip && \
    docker-php-ext-configure zip --with-libzip && \
    docker-php-ext-install zip && \
    php -m | grep -q 'zip'

# node
RUN curl -sL https://deb.nodesource.com/setup_13.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs npm

# composer install
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV PATH $PATH:/composer/vendor/bin

WORKDIR /var/www/html

# Laravel install
RUN composer global require "laravel/installer"