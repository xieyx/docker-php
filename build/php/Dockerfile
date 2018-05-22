FROM php:7.1-fpm

# other
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    git \
    openssl \
    libz-dev \
    libssl-dev \
    libmcrypt-dev \
    && rm -rf /var/lib/apt/lists/* \
    && cd /tmp/ \
    && git clone https://github.com/tideways/php-xhprof-extension.git \
    && cd php-xhprof-extension \
    && phpize \
    && ./configure --with-php-config=/usr/local/bin/php-config \
    && make \
    && make install \
    && cd /tmp/ \
    && rm -rf php-xhprof-extension \
    && pecl install yaf \
    && pecl install redis \
    && pecl install mongodb \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mcrypt \
    && docker-php-ext-enable redis

CMD ["php-fpm"]

EXPOSE 9000
