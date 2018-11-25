#set php base image
FROM php:7.2-fpm
LABEL author="mohebbi.sadegh@gmail.com"

# awoid Docker + Wordpress - getting this error “Fatal error: Uncaught Error: Call to undefined function mysql_connect()”
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli