FROM php:7.4-fpm-alpine

# prepare os
RUN apk add --update --no-cache zlib1g-dev g++ git libicu-dev zip libzip-dev zip libpng-dev libonig-dev nodejs npm
RUN npm install --global yarn
RUN docker-php-ext-install intl opcache pdo pdo_mysql \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip \
    && docker-php-ext-install exif \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install gd

# os customization
RUN echo "alias ll='ls \$LS_OPTIONS -l'" >> /root/.bashrc

# php Configuration
COPY symfony-docker.php.ini $PHP_INI_DIR/conf.d/symfony-docker.php.ini

WORKDIR /var/www/symfony_docker

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# install symfony-cli
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

# setup git
RUN git config --global user.email "you@example.com" \
    && git config --global user.name "Your Name"
