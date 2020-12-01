FROM yeszao/php:5.4.45-fpm-alpine
RUN apk update && apk upgrade

#RUN apk add -y php-common php-bcmath php-pecl-mongodb php-fpm php-cli php-gd php-intl php-opcache php-pdo php-pecl-imagick php-mbstring php-mcrypt php-mysql php-pecl-xdebug php-pgsql php-soap php-xml 

RUN docker-php-ext-install -j$(nproc) mysqli opcache bcmath pecl-mongodb fpm cli gd intl opcache pdo pecl-imagick mbstring mcrypt mysql pecl-xdebug pgsql soap xml 

RUN mkdir -p /var/www/edms
COPY ./edms/ /var/www/edms
RUN chown -R www-data:www-data /var/www/edms
WORKDIR /var/www/edms
ENV APACHE_DOCUMENT_ROOT /var/www/edms/

COPY ./conf/fcgid.conf /etc/httpd/conf.d/
COPY ./conf/demo-docs.itsec.md.conf /etc/httpd/conf.d/

CMD [ "php", "/var/www/edms/index.php" ]



