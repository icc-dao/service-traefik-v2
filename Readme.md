# ICCD Traefik
General traefik service for the ICCD hosts.

## Howto

### Install
``` 
docker-compose
docker.io
```

### Clone
```
$ mkdir -p /opt/services
$ cd /opt/services
$ git clone https://github.com/icc-dao/service-traefik-v2
```

### Configure
```
$ echo '{"ipv6":true,"fixed-cidr-v6":"fd00::/80","experimental":true,"ip6tables":true}' > /etc/docker/daemon.json
$ systemctl restart docker
$ docker network create --ipv6 --subnet fd8b:20d3:7f65:72ae::/64 traefik-v2-proxy
$ ./generate_config.sh
```

### Start
```
$ docker-compose up -d
```