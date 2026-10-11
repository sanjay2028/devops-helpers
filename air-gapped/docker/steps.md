## Required Files
containerd.io-1.6.28-3.1.el8.x86_64.rpm
docker-compose-plugin-2.25.0-1.el8.x86_64.rpm
docker-buildx-plugin-0.13.1-1.el8.x86_64.rpm
docker-ce-cli-26.0.0-1.el8.x86_64.rpm
docker-ce-26.0.0-1.el8.x86_64.rpm
container-selinux-2.229.0-2.module+el8.10.0+2001+6a33db9f.noarch.rpm
libcgroup-0.41-19.el8.x86_64.rpm

---- Steps to follow -----

## Check if podman in instaleld already especially on RHEL 8.1
podman --version

## If yes, then uninstall it using the following command
sudo dnf remove -y podman buildah skopeo runc

## Install the rpm files
sudo rmp -ivh *.rpm


$ sudo chown -aG docker $USER
$ newgrp docker
$ sudo systemctl enable docker 
$ sudo systemctl start docker
$ docker ps ## to validate the docker run command


## Commands to export tar file for docker image
docker image save \
	-o your-desired-image-name.tar \
	name_of_your_image 