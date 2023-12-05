# Docker install Commands on Ubuntu 22.04

$ ``sudo apt update``  
$ ``sudo apt upgrade``  
$ ``sudo apt install lsb-release ca-certificates apt-transport-https software-properties-common -y``  
$ ``curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg``  
$ ``echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null``  
$ ``sudo apt update``  
$ ``sudo apt install docker-ce``  
$ ``sudo systemctl status docker``  


Portainer Command:

$ ``mkdir docker``  
$ ``sudo docker volume create portainer_data``  
$ ``sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer \
    --net=host \
    --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data \
    portainer/portainer-ce:2.9.3``  
