FROM julienvincent/nginx
MAINTAINER Julien Vincent <julienlucvincent@gmail.com>

ENV PHP_VERSION 5.4.39-0+deb7u2

RUN \
    apt-get update && \
    apt-get -y install \
    php5-cli=${PHP_VERSION} \
    php5-fpm \
    php5-json \
    php5-mcrypt && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN mkdir -p /data/www

# Add configs
COPY container/php_restrictions.conf /etc/nginx/global/php_restrictions.conf
COPY container/static_asset_caching.conf /etc/nginx/global/static_asset_caching.conf
COPY container/php-fpm.conf /etc/nginx/php-fpm.conf
COPY container/php.ini /etc/php5/fpm/php.ini
COPY container/www.conf /etc/php5/fpm/pool.d/www.conf
COPY container/default.conf /etc/nginx/conf.d/default.conf

COPY container/supervisord.conf /etc/supervisor/conf.d/supervisord.conf

COPY container/index.php /data/www/index.php

# Container Config
CMD ["/usr/bin/supervisord"]
EXPOSE 80 443