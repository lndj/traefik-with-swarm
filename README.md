<p align="center">
# Traefix Proxy With Docker Swarm
</p>

A traefik demo with docker swarm for little / personal project.

# Feature

1. Auto https With Let's encrypt.
2. Auto loadbalance.

# Getting started

1. Create a docker network 

```shell
docker network create -d overlay proxy-net
```
More info: (Docker network doc)[https://docs.docker.com/engine/reference/commandline/network_create/]

2. Create traefik stack

```shell
docker swarm init

docker stack  deploy -c traefik-proxy-compose.yml traefik-proxy
```

3. Start your service

```shell
docker stack  deploy -c service-compose.yml my-service
```
