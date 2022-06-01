FROM php:7.0.28-apache
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
  && apt-get clean \
  && rm -r /var/lib/apt/lists/* \
  && docker-php-ext-configure gd \
  && docker-php-ext-install pdo pdo_mysql mbstring gd intl zip \
  && a2enmod rewrite

