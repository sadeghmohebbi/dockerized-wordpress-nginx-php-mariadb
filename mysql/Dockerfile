#set mysql base image
FROM mariadb:10.3
LABEL author="mohebbi.sadegh@gmail.com"

ENV MYSQL_ROOT_PASSWORD=#9ZQK*LA2VTe6YNKkXL2UPGax$@tP@D3

ENV MYSQL_USER=wp_user

ENV MYSQL_PASSWORD=123456

ENV MYSQL_DATABASE=wordpress

COPY ./wordpress.sql /docker-entrypoint-initdb.d/
# RUN /etc/init.d/mysql start && mysql -u root --password="shJphC67EZ8" "GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'shJphC67EZ8'"