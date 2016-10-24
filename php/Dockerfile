FROM php:fpm
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng12-dev \
    libmysqlclient-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt mysqli opcache bcmath pdo pdo_mysql mbstring \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
COPY upload_max_filesize.ini /usr/local/etc/php/conf.d/
