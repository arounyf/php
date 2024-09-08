FROM php:7.4-fpm-alpine3.16
#换源
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
#安装tadata
RUN apk add tzdata
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install mysqli