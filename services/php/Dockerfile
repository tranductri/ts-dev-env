FROM php:5.6-fpm

RUN docker-php-ext-install pdo pdo_mysql mysqli sockets
RUN apt-get update -y \
  && apt-get install -y \
    libxml2-dev \
	libfreetype6-dev \
	libjpeg62-turbo-dev \
	libmcrypt-dev \
	libpng12-dev \
    php-soap \
  && apt-get clean -y \
  && docker-php-ext-install soap \
  && docker-php-ext-install -j$(nproc) iconv mcrypt \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
  && docker-php-ext-install -j$(nproc) gd