#set php base image
FROM php:7.2-fpm
LABEL author="mohebbi.sadegh@gmail.com"

# avoid permission error for write file
RUN chown -R www-data:www-data /var/www
RUN find /var/www/ -type d -exec chmod 0755 {} \;
RUN find /var/www/ -type f -exec chmod 644 {} \; 

# awoid Docker + Wordpress - getting this error “Fatal error: Uncaught Error: Call to undefined function mysql_connect()”
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli