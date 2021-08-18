### Steps installasi Docker
$ sudo apt update

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

$ sudo apt update

$ sudo apt install docker-ce

$ sudo systemctl status docker

sudo service docker status
sudo /etc/init.d/docker start
service --status-all

$ sudo usermod -aG docker ${USER}

$ su - ${USER}

$ id -nG

$ sudo usermod -aG docker <USER>

#### Docker Compose

$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

$ sudo chmod +x /usr/local/bin/docker-compose

$ docker-compose --version


I had the same problem. I assume that you are using Docker Docs, which are usually outdated. You should go to Docker Compose Github instead.

Solution

1 - Open Linux Terminal by pressing Ctrl + Alt + T

2 - Install curl:

sudo apt install curl
3 - Turn on root privileges in terminal for your user (something like admin in Windows OS), with command:

sudo -i
4 - Go to Docker Compose Github. In releases you will find this code. Run it in your linux terminal.

curl -L https://github.com/docker/compose/releases/download/1.25.1-rc1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
5 - Turn off root privileges in terminal for your user, with command:

exit
6 - Check if docker-compose is installed with command:

docker-compose version
Outcome: In your terminal, you should see docker-compose version number and some other informations.

[Install Docker Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
[Install Docker Compose Cross Distro](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

### How using docker
- check status = sudo service docker status
- check start docker = sudo service docker start

- list container on = docker ps
- list all container = docker ps -a

- stop docker container = docker stop id
- delete docker container = docker rm id
- flush cache = docker system prune

- buka vs code wsl = code .
- to open folder in wsl = explorer.exe .
- change permisson file = sudo chmod +rwx mysql_images.docker


- run docker = docker run --name docker-nginx -p 6969:80 nginx
- run docker = docker run -d -t -p 1230:80 --name c01 nginx ( sama aja )

### How to move file from windows to linux using pscp
- cd Desktop
- dir
- pscp -P 22 file root@ipaaddres server:/root/

- change dir = cd directory
- edit file = sudo nano namafile


## steps docker mengatasi error ( ini masalah permission file atau ownership file, masih belum nemu solusi yang terbaik)
- ubah permission semua file : chmod -R 777 ./ atau chmod -R 777 /www/
- masukin databasenya
- Host nya ganti nama service di docker compose di file php confignya

## Backup database
- docker exec CONTAINER /usr/bin/mysqldump -u root --password=password DATABASE > haccp-dashboard.sql

## Masukin database container ada beberapa cara tested on mysql:5.6
- bisa pake mysql workbench, tinggal masukin nama host dan port (ini enak gampang lagi)

- bisa pake command langsung
    - cat backup.sql | docker exec -i CONTAINER /usr/bin/mysql -u root --password=root DATABASE
    - docker exec -i your_container_id mysql -u root -p(password) your_db_name < /your_project_folder/backup.sql (tergantung kalian naro filenya dimana)
        - kalian nanti bisa lihat hasil dbnya di folder docker mysql = file > var > lib > mysql > nama db kalian