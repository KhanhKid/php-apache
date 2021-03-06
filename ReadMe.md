# php-apache Supported tags
This repo used in Dockerhub url 'https://cloud.docker.com/repository/docker/wsgroup/php5.6-apache-b2b'
* latest [Link to Dockerfile](https://github.com/KhanhKid/php5.6-apache-b2b/tree/master)

## Module install in images
* gd
* iconv
* mcrypt
* intl
* mysql
* mysqli
* pdo_mysql
* zip
* mbstring
* mod_rewrite

## External extension
* Memcached
* Composer
* OpenSSL
* Imagick

## Volume
* /var/www
* /var/log/apache2
* /etc/apache2/sites-enabled

## Port
* 80
* 443

## How to use with Docker
```
docker run --name testphp -p 8080:80 -d -v $(pwd):/var/www/html docker push wsgroup/php5.6-apache-b2b
```
## Use with Docker-compose 
```
  apache:
    image: wsgroup/php5.6-apache-b2b
    container_name: apache
    ports:
      - "80:80"
    volumes:
      - ./apache2/conf:/etc/apache2/sites-enabled
      - ./apache2/www:/var/www
      - ./apache2/logs:/var/log/apache2
    environment:
      - TZ=Asia/Bangkok
    restart: always
```

** Cloned from:https://github.com/porchn/php5-apache/tree/pdftk
