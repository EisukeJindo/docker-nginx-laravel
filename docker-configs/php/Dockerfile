FROM php:5.6-fpm

RUN apt-get update -y && apt-get install -y libpng-dev libjpeg-dev zip unzip git
RUN docker-php-ext-configure gd \
    --with-jpeg-dir=/usr/lib/x86_64-linux-gnu/ \
    && docker-php-ext-install pdo pdo_mysql gd mbstring

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
#composer高速化ライブラリ
RUN composer global require "hirak/prestissimo:^0.3"
