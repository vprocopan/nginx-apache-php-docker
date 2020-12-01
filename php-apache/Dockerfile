FROM yeszao/php:5.4.45-fpm-alpine
RUN yum install https://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN yum install -y yum-config-manager
RUN yum-config-manager --enable remi-php54
RUN yum update -y

RUN yum install -yphp-common php-bcmath php-pecl-mongodb php-fpm php-cli php-gd php-intl php-opcache php-pdo php-pecl-imagick php-mbstring php-mcrypt php-mysql php-pecl-xdebug php-pgsql php-soap php-xml 

RUN mkdir -p /var/www/edms
COPY ./edms/ /var/www/edms
RUN chown -R www-data:www-data /var/www/edms
WORKDIR /var/www/edms
ENV APACHE_DOCUMENT_ROOT /var/www/edms/

COPY ./conf/fcgid.conf /etc/httpd/conf.d/
COPY ./conf/demo-docs.itsec.md.conf /etc/httpd/conf.d/

CMD [ "php", "/var/www/edms/index.php" ]



