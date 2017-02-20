FROM php:5.6-fpm

RUN apt-get update -y && apt-get install -y locales dialog
RUN localedef -i ja_JP -c -f UTF-8 -A /usr/share/locale/locale.alias ja_JP.UTF-8
ENV LANG ja_JP.utf8

RUN apt-get install -y libpng-dev libjpeg-dev zip unzip git
RUN docker-php-ext-configure gd \
    --with-jpeg-dir=/usr/lib/x86_64-linux-gnu/ \
    && docker-php-ext-install pdo pdo_mysql gd mbstring

RUN usermod -u 1000 www-data \
   && groupmod -g 1000 www-data

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
#composer高速化ライブラリ
RUN composer global require "hirak/prestissimo:^0.3"
