FROM devilbox/php-fpm:5.4-prod

RUN mkdir -p /var/www/edms
COPY ./edms/ /var/www/edms
RUN chown -R www-data:www-data /var/www/edms

ENV APACHE_DOCUMENT_ROOT /var/www/edms/

COPY ./conf/fcgid.conf /etc/httpd/conf.d/
COPY ./conf/demo-docs.itsec.md.conf /etc/httpd/conf.d/

#CMD [ "php", "/var/www/edms/index.php" ]



