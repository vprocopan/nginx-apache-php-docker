FROM yeszao/php:5.4.45-fpm-alpine
RUN mkdir /edms
COPY /edms/ /edms/
RUN chown -R apache:apache /edms/
WORKDIR /edms/
CMD [ "php", "/edms/index.php" ]