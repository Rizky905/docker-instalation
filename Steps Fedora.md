### Steps

$ sudo dnf -y install dnf-plugins-core

$ sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo

$ sudo dnf install docker-ce docker-ce-cli containerd.io

$ dnf list docker-ce  --showduplicates | sort -r

$ sudo dnf -y install docker-ce-<VERSION_STRING> docker-ce-cli-<VERSION_STRING> containerd.io

$ sudo systemctl start docker

$ sudo usermod -aG docker ${USER}

$ su - ${USER}

$ id -nG

$ sudo usermod -aG docker <USER>

[Install Docker Fedora](https://docs.docker.com/engine/install/fedora/)