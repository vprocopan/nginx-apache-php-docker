FROM yeszao/php:5.4.45-fpm-alpine
RUN mkdir /edms
COPY /edms/ /edms/
RUN chown -R apache:apache /edms/
WORKDIR /edms/
ENV APACHE_DOCUMENT_ROOT /edms/

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/httpd/conf/*.conf
RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/httpd/conf/httpd.conf /etc/httpd/conf.d/*.conf

CMD [ "php", "/edms/index.php" ]



