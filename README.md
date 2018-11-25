![](https://s.w.org/style/images/about/WordPress-logotype-wordmark.png)

# wordpress+nginx+php+mariadb with docker

## 1. install requirements

first of all you need to install docker and docker compose, you can find it in [docker documentation](https://docs.docker.com/install/) and [docker compose documentation](https://docs.docker.com/compose/install/)

## 2. clone this repo
<code>cd ~ && git clone https://github.com/sadeghmohebbi/dockerized-wordpress-nginx-php-mariadb.git</code>

## 3. edit mariadb dockerfile file
use your own password and envs in [this file (mysql/Dockerfile)](https://github.com/sadeghmohebbi/dockerized-wordpress-nginx-php-mariadb/blob/master/mysql/Dockerfile)

## 4. run it
use commands below in root directory. default provided docker compose file can be used

<code>$ docker-compose up -d --build</code>

to see what happens:

<code>$ docker-compose logs -f</code>

## 5. install worpress
first of all give permission to nginx container to write file (avoiding permission issue) according to [this stackoverflow question](https://stackoverflow.com/questions/44251019/wordpress-on-docker-could-not-create-directory-on-mounted-volume)

<code>$ docker exec -it CONTAINER_ID /bin/bash</code>

inside nginx docker image use this commands:

<code>$ mkdir /var/www/html/wp-content/plugins</code>

<code>$ mkdir /var/www/html/wp-content/uploads</code>

<code>$ chown -R www-data:www-data /var/www</code>

<code>$ find /var/www/ -type d -exec chmod 0755 {} \;</code>

<code>$ find /var/www/ -type f -exec chmod 644 {} \;</code>

and then get worpress version you want from [official website](https://wordpress.org/download/) or simply use commands below:

<code>$ cd ~ && wget https://wordpress.org/latest.tar.gz && tar -xvf latest.tar.gz</code>

<code>$ yes | cp -r wordpress/* dockerized-wordpress-nginx-php-mariadb/public_html</code>

## 6. last step
use **mysql** as a mysql host name and **wordpress** as a database name, other values are based on your configuration in mysql dockerfile (step 3)
