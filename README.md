Use Lubuntu Base virtualbox image

# Enable copy and paste in VM
Menu => Devices => Insert Guest Additions CD image

_if cannot, go add optical drive under storage and choose the VBoxGuestAdditions.iso_

cd /media/analyst/VBox_GAs_7.1.4/
sudo ./VBoxLinuxAdditions.run
sudo reboot

# Install docker and docker compose
sudo apt update

sudo apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"

sudo apt update

apt-cache policy docker-ce

sudo apt install docker-ce

sudo systemctl status docker

sudo usermod -aG docker ${USER}

sudo curl -L https://github.com/docker/compose/releases/download/1.29.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

# Install Chromium browser
sudo apt install chromium-browser

# Clone repository and setup container

git clone https://github.com/hanley/IOS.git

cd IOS

sudo docker-compose up

# To use the platform

localhost:8502

# To load model

localhost:3002
