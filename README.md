<h1 align="center">
Traefix Proxy With Docker Swarm
</h1>

A traefik demo with docker swarm for little / personal project (You don't need k8s).

# Feature

1. Auto https With Let's encrypt.
2. Auto load balance.
3. Proxy dashboard.

# Getting started

1. Create a docker network 

```shell
docker network create -d overlay proxy-net
```
More info: [Docker document](https://docs.docker.com/engine/reference/commandline/network_create/)

2. Create traefik stack

```shell
docker swarm init

docker stack  deploy -c traefik-proxy-compose.yml traefik-proxy
```

3. Start your service

```shell
docker stack  deploy -c service-compose.yml my-service
```

# Remark

When use traefik dashboard with http basic auth, use this command generate password:

```shell
echo $(htpasswd -nb user yourpassword) | sed -e s/\\$/\\$\\$/g
```
