## 👋 Welcome to archlinux 🚀  

archlinux README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update archlinux
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/archlinux/rootfs"
git clone "https://github.com/dockermgr/archlinux" "$HOME/.local/share/CasjaysDev/dockermgr/archlinux"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/archlinux/rootfs/." "$HOME/.local/share/srv/docker/archlinux/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdev-archlinux \
--hostname archlinux \
-e TZ=${TIMEZONE:-America/New_York} \
casjaysdev/archlinux:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/archlinux
    container_name: casjaysdev-archlinux
    environment:
      - TZ=America/New_York
      - HOSTNAME=archlinux
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdev/archlinux
```
  
OR
  
```shell
git clone "https://github.com/casjaysdev/archlinux" "$HOME/Projects/github/casjaysdev/archlinux"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdev/archlinux"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/casjaysdev) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  
