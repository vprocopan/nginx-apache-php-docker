FROM marcelosantoro/php-5.4.45-fpm:5.4.45-fpm
RUN rpm -Uvh https://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN yum update
# Install php extensions
RUN yum update --disablerepo=base
RUN yum-config-manager --enable remi-php54
RUN yum install -y yum-config-manager php-common php-bcmath php-pecl-mongodb php-fpm php-cli php-gd php-intl php-opcache php-pdo php-pecl-imagick php-mbstring php-mcrypt php-mysql php-pecl-xdebug php-pgsql php-soap php-xml 




RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"
COPY ./conf/php-conf.ini $PHP_INI_DIR/conf.d/

ENV APACHE_DOCUMENT_ROOT /home/vprocopan/edms

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/httpd/conf/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

# vinhjaxt
RUN sed -i -E 's/Listen\s+80([^0-9]|$)/Listen 8080\1/g' /etc/conf.d/*.conf /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

RUN sed -i -E 's/(VirtualHost\s+.+)\:80([^0-9]|$)/\1:8080\2/g' /etc/conf.d/*.conf /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

