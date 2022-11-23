Lo primero que debemos de hacer es instalar docker-compose

sudo apt install docker-compose

Ahora creamos el archivo docker-compose.yaml

version: '3'

services:
    db:
        image: mariadb:10.3.9
        volumes:
            - data:/var/lib/mysql
        environment:
            - MYSQL_ROOT_PASSWORD=secret
            - MYSQL_DATABASE=wordpress
            - MYSQL_USER=manager
            - MYSQL_PASSWORD=secret
    web:
        image: wordpress:4.9.8
        depends_on:
            - db
        volumes:
            - ./target:/var/www/html
        environment:
            - WORDPRESS_DB_USER=manager
            - WORDPRESS_DB_PASSWORD=secret
            - WORDPRESS_DB_HOST=db
        ports:
            - 8080:80

volumes:
    data:

Ejecutamos el doker-compose y miramos si se a creado

sudo docker-compose up -d

docker-compose ps

Una vez ejecutado podemos entrar a http://localhost:8080/ para instalar wordpress con la interfaz gráfica

http://localhost:8080/

Para ver el volumen de datos creado para worlpress

sudo docker volume ls

Iniciamos los servicios con los siguientes 2 comandos 
sudo docker run -d --name wordpress-db \
        --mount source=wordpress-db,target=/var/lib/mysql \
        -e MYSQL_ROOT_PASSWORD=secret \
        -e MYSQL_DATABASE=wordpress \
        -e MYSQL_USER=manager \
        -e MYSQL_PASSWORD=secret mariadb:10.3.9

sudo docker run -d --name wordpress-db \
    --restart unless-stopped
    --mount source=wordpress-db,target=/var/lib/mysql \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=wordpress \
    -e MYSQL_USER=manager \
    -e MYSQL_PASSWORD=secret mariadb:10.3.9



