### Steps
sudo service docker status
sudo service docker start
#### Docker
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


to open file in wsl :
explorer.exe .

change permisson file :
sudo chmod +rwx mysql_images.docker

docker run --name docker-nginx -p 6969:80 nginx
$ docker run -d -t -p 1230:80 --name c01 nginx

cara mindahin file dari windows ke linux using pscp
- cd Desktop
- dir
- pscp -P 22 file root@ipaaddres server:/root/

remove docker container 
docker container rm id