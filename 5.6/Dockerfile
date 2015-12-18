FROM php:5.6-fpm

RUN apt-get update && apt-get install -y \
      libfreetype6-dev \
      libjpeg62-turbo-dev \
      libmcrypt-dev \
      libpng12-dev \
  && docker-php-ext-install iconv mcrypt mbstring gd mysqli pdo pdo_mysql \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

RUN usermod -u 1000 www-data
RUN usermod -G staff www-data

CMD ["php-fpm"]
