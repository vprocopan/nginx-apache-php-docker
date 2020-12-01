FROM nginx:alpine
RUN mkdir /etc/nginx/ssl

COPY ./conf/default.conf /etc/nginx/conf.d/default.conf
COPY /home/vprocopan/cert/* /etc/nginx/ssl/


# CMD ["nginx-debug", "-g", "daemon off;"]
# CMD ["nginx", "-g", "daemon off;"]
