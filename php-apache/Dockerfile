FROM marcelosantoro/php-5.4.45-fpm:5.4.45-fpm
RUN yum update
# Install php extensions
RUN pecl install redis && docker-php-ext-enable redis
RUN docker-php-ext-install mysqli bcmath fpm cli gd intl opcache pdo pecl-imagick mbstring mcrypt mysql pecl-xdebug pgsql soap xml && docker-php-ext-enable mysqli bcmath fpm cli gd intl opcache pdo pecl-imagick mbstring mcrypt mysql pecl-xdebug pgsql soap xml


RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"
COPY ./conf/php-conf.ini $PHP_INI_DIR/conf.d/

ENV APACHE_DOCUMENT_ROOT /home/vprocopan/edms

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/httpd/conf/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

# vinhjaxt
RUN sed -i -E 's/Listen\s+80([^0-9]|$)/Listen 8080\1/g' /etc/conf.d/*.conf /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

RUN sed -i -E 's/(VirtualHost\s+.+)\:80([^0-9]|$)/\1:8080\2/g' /etc/conf.d/*.conf /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

