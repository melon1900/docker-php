FROM melonli/php

RUN set -xe && \
    apt-get update && apt-get install -y python-setuptools git unzip \
    && rm -r /var/lib/apt/lists/* \
    && easy_install supervisor \
    && curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer \
    && composer create-project --prefer-dist laravel/laravel /var/www/html 5.2.* \
    && cd /var/www/html \
    && composer require --prefer-dist "aws/aws-sdk-php ~3.0" \
    && composer require --prefer-dist "pda/pheanstalk ~3.0" \
    && composer require --prefer-dist "predis/predis ~1.0" 

CMD ["supervisord", "-n", "-c", "/etc/supervisord.conf"]
