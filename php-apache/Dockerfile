FROM yeszao/php:5.4.45-fpm-alpine
RUN mkdir /home/edms
COPY /edms /home/edsm/
WORKDIR /home/edms/
CMD [ "php", "/home/edms/index.php" ]