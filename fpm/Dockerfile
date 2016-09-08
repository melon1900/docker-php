FROM php:7.0-fpm
RUN set -xe && \
	apt-get update && apt-get install -y \
        libmcrypt-dev \
        libmhash-dev \
        libcap-dev \
    && rm -r /var/lib/apt/lists/* \
    && docker-php-ext-install -j$(nproc) iconv mcrypt mysqli pdo pdo_mysql sockets 
