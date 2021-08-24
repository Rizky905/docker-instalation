## docker-instalation untuk penggunaan offline jika ketemu error GD instalation & ZipArchive di php

# install dulu di local linux kalian yang ada internetnya
- download folder base-php-GDImage-Zarchiever 
- pindah ke folder yang didonwload tadi 
- docker-compose up 
- backup images => steps ada di file docker steps

# restore images tadi ke server yang tidak ada internetnya
- semua steps restore ada di folder docker steps

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





