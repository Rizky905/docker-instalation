### Steps
akses internet di server
export http_proxy=http://10.203.121.171:80

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


[Install Docker Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
[Install Docker Compose Cross Distro](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)