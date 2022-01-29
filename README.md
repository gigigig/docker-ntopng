# docker-ntopng
Docker configuration set-up for ntopng.

## Set up Portainer

https://docs.portainer.io/v/ce-2.11/start/install/server/docker/linux \
https://hub.docker.com/r/portainer/portainer-ce

```
docker volume create portainer_data
sudo docker run \
    -d \
    -p 9443:9443 \
    --name=portainer \
    --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data \
    portainer/portainer-ce
```

Browse to https://HOSTNAME:9443/ for setup.

## ntopng

https://hub.docker.com/r/ntop/ntopng

```
sudo mkdir -m 777 -p /var/lib/ntopng
```

[docker\_compose.yml](docker-compose.yml)

Browse to http://HOSTNAME:3000 for setup.
