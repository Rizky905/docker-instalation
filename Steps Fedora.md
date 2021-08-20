### Steps
cek installed rpm => rpm -qa | grep docker

sudo systemctl status ssh
ip server 10.203.121.171
user/pass nya 
root/P@ssw0rd@danone

### akses internet di server
- export http_proxy=http://ipaddres dari server:80
- export https_proxy=http://ipaddres dari server:80
- cek proxy yang dipake => env | grep -i proxy

### saving and quit file using vi/vim :
- click => i untuk insert text
- esc => untuk keluar 
- ketik => :wq untuk save and quit


### change dns nameserver
- vim /etc/resolv.conf
- namesever di danone pake remote server windows
- nameserver 10.203.121.3 -> 8.8.8.8
- nameserver 10.203.57.120 -> 8.8.4.4
https://www.cyberciti.biz/faq/change-dns-ip-address-rhel-redhat-linux/
https://wiseindy.com/blog/linux/how-to-set-dns-in-centos-rhel-7-prevent-network-manager-from-overwriting-etc-resolv-conf/
https://computingforgeeks.com/configure-system-wide-proxy-settings-on-centos-rhel-fedora/
https://stackoverflow.com/questions/23111631/cannot-download-docker-images-behind-a-proxy
https://docs.docker.com/engine/install/rhel/
https://docs.docker.com/config/daemon/systemd/
https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html/getting_started_with_containers/index
https://computingforgeeks.com/install-and-configure-docker-registry-on-centos-7/
https://viandwi24.medium.com/belajar-docker-mengenal-apa-itu-registry-images-docker-host-docker-client-docker-engine-4e085baa22c4


### install docker image without internet :
https://stackoverflow.com/questions/48125169/how-run-docker-images-without-connect-to-internet
https://serverfault.com/questions/701248/downloading-docker-image-for-transfer-to-non-internet-connected-machine
https://dev.to/ajeet/so-you-have-installed-windows-subsystem-for-linux-let-s-learn-how-to-move-files-inside-of-linux-root-system-4kbo

- download image from your pc => exp : docker pull php
- save image => exp : sudo docker save -o php_image.docker php
- jika mengalami error permission saat mindahin file dari download => exp : sudo chmod +rwx php_images.docker
- transfer file from your pc into server using PSCP (Putty) 
    - cd File yang lu simpen tadi dimana
    - dir
    - pscp -P 22 file root@10.203.121.171:/root/
- setelah selesai copy file => exp : sudo docker load -i php_image.docker

### install docker compose offline :
http://muralitechblog.com/how-to-install-docker-compose-offline/

- download dulu docker-composenya di pc yang ada internet
    => https://github.com/docker/compose/releases bisa dipilih versinya , kalo untuk semua jenis os yang basenya linux bisa pake yang ini
        docker-compose-Linux-x86_64

- copy file ke server, caranya sama pake pscp

- setelah file ada di server ganti permissionnya 
    - mv docker-compose /usr/local/bin/
    - chmod +x /usr/local/bin/docker-compose

- systemctl status docker.service


### jika server bisa akses koneksi keluar
docker pull php

systemctl list-unit-files | grep docker

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