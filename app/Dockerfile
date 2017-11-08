FROM php:5.6-fpm

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
ENV DOCKER true

RUN rm -rf /usr/local/etc/php-fpm.d
RUN mkdir /var/run/php-fpm

RUN apt-get update
RUN apt-get install -y mysql-client vim net-tools telnet curl

RUN \
    docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd --with-libdir=lib/x86_64-linux-gnu/ \
    && docker-php-ext-configure mysqli --with-mysqli=mysqlnd --with-libdir=lib/x86_64-linux-gnu/ \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install pdo_mysql
