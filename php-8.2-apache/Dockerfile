FROM php:8.2-apache
RUN apt-get update \
  && apt-get install --no-install-recommends -y \
     libpng-dev \
     libfreetype6-dev \
     libjpeg-dev \
     libpng-dev \
     zlib1g-dev \
     libicu-dev \
     libonig-dev \
     libzip-dev \
     zip \
     wget \
     vim \
     unzip \
     libxml2-dev \
     default-mysql-client \
     git \
     jq \
  && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
  && apt-get clean \
  && rm -r /var/lib/apt/lists/* \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install pdo pdo_mysql mbstring gd intl zip soap \
  && echo 'memory_limit = 2048M' >> /usr/local/etc/php/conf.d/php-base.ini \
  && echo 'max_upload_size=50M' >> /usr/local/etc/php/conf.d/php-base.ini \
  && echo 'post_max_size=50M' >> /usr/local/etc/php/conf.d/php-base.ini \
  && a2enmod rewrite
