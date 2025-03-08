# --- *** portainer docker admin with Docker in Linux Mint 21. *** --- #

--- official web site address ---
https://hub.docker.com/r/portainer/portainer
https://docs.portainer.io/start/install-ce/server/docker/linux

--- github repo ---
https://github.com/ggvhcs/portainer

--- youtube ---
https://youtu.be/pPXuljQMlLs

Develop Enviroment:
---
Linux Mint 21.2 Mate x64.
Docker version 24.0.7, build 24.0.7-0ubuntu2~22.04.1
git version 2.34.1
Github Desktop version 3.2.0-linux1 (x64)
Visual Studio Code version 1.96.4
---

1 --- download image portainer from hub docker ---
$ sudo docker pull portainer/portainer-ce:lts
$ sudo docker pull portainer/portainer
$ sudo docker images |grep portainer

$ sudo docker volume ls
$ sudo docker volume rm portainer_data // delete portainer_data volume if exist before.
$ sudo docker volume create portainer_data
$ sudo docker volume ls
---
DRIVER    VOLUME NAME
local     portainer_data
---

--- ! you can use this image if you want. ---
$ sudo docker run -d -p 8000:8000 -p 9443:9443 \
--name portainer --restart=always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data portainer/portainer

--- I always used this. ---
sudo docker run -d -p 8000:8000 -p 9443:9443 \
--name portainer --restart=always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data portainer/portainer-ce:lts

$ sudo docker ps

https://localhost:9443

user -> admn
pass --> blabla2025**

--- running again. ---
$ sudo docker start portainer

# --- *** portainer docker admin in Linux Mint 21 running OK. *** --- #
