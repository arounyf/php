# php74-fpm
- 设置了系统和PHP时区为Asia/Shanghai
- 安装了mysqli、pdo_mysql
- 安装了php-Composer
- 修改工作目录为/www

# 构建镜像
`docker build . -t runyf/php:7.4-fpm`

# 说明
本仓库基于官方Dockerfile进行了修改，官方参考链接如下   
https://github.com/docker-library/php/tree/b9f17156020c3aef71df681b27684533529347a7/7.4/bullseye/fpm
