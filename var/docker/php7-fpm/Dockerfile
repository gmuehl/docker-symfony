FROM alpine:latest

RUN apk add --update --no-cache \
    coreutils \
    php7-fpm \
    php7-apcu \
    php7-ctype \
    php7-curl \
    php7-dom \
    php7-gd \
    php7-iconv \
    php7-imagick \
    php7-json \
    php7-intl \
    php7-mcrypt \
    php7-fileinfo\
    php7-mbstring \
    php7-opcache \
    php7-openssl \
    php7-pdo \
    php7-pdo_mysql \
    php7-mysqli \
    php7-xml \
    php7-zlib \
    php7-phar \
    php7-tokenizer \
    php7-session \
    php7-simplexml \
    php7-xdebug \
    php7-xmlwriter \
    php7-zip \
    make \
    curl

RUN apk add --update --no-cache \
    ca-certificates \
    msmtp

RUN apk add --update --no-cache \
    bash

RUN echo 'alias sf3="php bin/console"' >> ~/.bashrc
RUN ln -sf /usr/bin/msmtp /usr/sbin/sendmail

COPY symfony.ini /etc/php7/conf.d/
COPY symfony.ini /etc/php7/cli/conf.d/
COPY symfony.pool.conf /etc/php7/php-fpm.d/
COPY msmtprc /etc/

CMD ["php-fpm7", "-F"]

WORKDIR /var/www/symfony
EXPOSE 9001
