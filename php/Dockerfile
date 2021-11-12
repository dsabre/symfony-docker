FROM php:7.4-fpm-alpine

WORKDIR /var/www/symfony_docker

# prepare os
RUN apk add --no-cache \
    coreutils \
    curl \
    icu-dev \
    freetype \
    libjpeg-turbo \
    libpng \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    git \
    zip \
    libzip-dev \
    oniguruma-dev \
    nodejs \
    npm \
    bash \
    $PHPIZE_DEPS

RUN docker-php-ext-install \
    intl \
    opcache \
    pdo \
    pdo_mysql \
    zip \
    exif \
    mbstring \
    gd
RUN docker-php-ext-configure zip
RUN pecl install apcu && docker-php-ext-enable apcu
RUN npm install --global yarn

# php Configuration
COPY php.ini $PHP_INI_DIR/php.ini

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# setup git
RUN git config --global user.email "you@example.com" \
    && git config --global user.name "Your Name"

# install symfony-cli
RUN wget https://get.symfony.com/cli/installer -O - | bash \
    && mv /root/.symfony/bin/symfony /usr/local/bin/symfony

# os customization
RUN echo "PS1=\"[\u@\h \W]\$ \"" >> /root/.bashrc
RUN echo "alias ll='ls \$LS_OPTIONS -l'" >> /root/.bashrc
