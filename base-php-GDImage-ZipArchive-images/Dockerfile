FROM php:7.3.27-fpm

WORKDIR /app/www

RUN docker-php-ext-install pdo pdo_mysql mysqli && docker-php-ext-enable mysqli

# Install system dependencies for GD
RUN apt-get update && apt-get install -y libpng-dev 
RUN apt-get install -y \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev libxpm-dev \
    libfreetype6-dev

RUN docker-php-ext-configure gd \
    --with-gd \
    --with-webp-dir \
    --with-jpeg-dir \
    --with-png-dir \
    --with-zlib-dir \
    --with-xpm-dir \
    --with-freetype-dir

RUN docker-php-ext-install gd 

# Install system dependencies for zarchiver
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

RUN apt-get update && \
    apt-get install -y \
    libzip-dev \
    && docker-php-ext-install zip
# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# CMD ["haccpboard-php", "-S", "0.0.0.0:80"]
# export http_proxy=http://10.203.130.36:8089