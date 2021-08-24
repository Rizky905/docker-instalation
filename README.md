## docker-instalation untuk penggunaan offline jika ketemu error GD instalation & ZipArchive di php

# install dulu di local linux kalian yang ada internetnya
- download folder base-php-GDImage-Zarchiever 
- pindah ke folder yang didonwload tadi 
- docker-compose up 
- backup images => steps ada di file [docker steps](https://github.com/Rizky905/docker-instalation/blob/master/Steps%20Fedora.md)

# restore images tadi ke server yang tidak ada internetnya
- semua steps restore ada di file [docker steps](https://github.com/Rizky905/docker-instalation/blob/master/Steps%20Fedora.md)

# file docker-compose.yml untuk aplikasi yang akan kalian gunakan
```sh
version: "3"
services:
  nginx: 
    image: nginx:latest
    container_name: project-nginx
    ports:
      - 7001:80
    links:
      - php
    depends_on:
      - php
    volumes:
      - "./nginx:/etc/nginx/conf.d/"
      - ".:/app"

  php:
    image: base_php:latest
    container_name: project-php
    volumes:
      - ".:/app"
  
  mysql:
    image: mysql:5.6
    container_name: project-mysql
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: database
    ports:
      - "3307:3306"
```





