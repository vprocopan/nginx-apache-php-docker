FROM nginx:alpine
RUN mkdir /etc/nginx/ssl

COPY ./conf/default.conf /etc/nginx/conf.d/default.conf
COPY /home/vprocopan/cert/cert.pem /etc/nginx/ssl/cert.pem
COPY /home/vprocopan/cert/key.pem /etc/nginx/ssl/key.pem


# CMD ["nginx-debug", "-g", "daemon off;"]
# CMD ["nginx", "-g", "daemon off;"]
