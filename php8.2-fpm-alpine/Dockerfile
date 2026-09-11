FROM php:8.2-fpm-alpine
#换源
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories
#安装tzdata并从底层设置系统时区(容器date命令也正确)
RUN apk add --no-cache tzdata \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone
#PHP时区
RUN printf '[PHP]\ndate.timezone = Asia/Shanghai\n' > /usr/local/etc/php/conf.d/tzone.ini
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install mysqli
#worker回收与超时（防止进程泄漏导致假死）
RUN sed -i 's/;pm.max_requests = 500/pm.max_requests = 500/' /usr/local/etc/php-fpm.d/www.conf \
    && sed -i 's/;request_terminate_timeout = 0/request_terminate_timeout = 30s/' /usr/local/etc/php-fpm.d/www.conf