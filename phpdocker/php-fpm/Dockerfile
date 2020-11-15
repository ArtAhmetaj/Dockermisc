FROM phpdockerio/php74-fpm:latest
WORKDIR "/application"
RUN apt-get update && apt-get install -y \
   libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd
# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive
