sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
# optional
#sudo yum-config-manager --enable docker-ce-edge
#sudo yum-config-manager --enable docker-ce-test
sudo yum install docker-ce
sudo systemctl start docker
# test:
sudo docker run hello-world
