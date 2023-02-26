## 👋 Welcome to ubuntu 🚀  

ubuntu README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update ubuntu
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/ubuntu/dataDir"
git clone "https://github.com/dockermgr/ubuntu" "$HOME/.local/share/CasjaysDev/dockermgr/ubuntu"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/ubuntu/dataDir/." "$HOME/.local/share/srv/docker/ubuntu/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/ubuntu:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-ubuntu \
--hostname casjaysdev-ubuntu \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/ubuntu/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/ubuntu/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/ubuntu:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  ubuntu:
    image: casjaysdevdocker/ubuntu
    container_name: ubuntu
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-ubuntu
    volumes:
      - $HOME/.local/share/srv/docker/ubuntu/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/ubuntu/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
