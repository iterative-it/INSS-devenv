# INSS-devenv
Docker files, scripts and utils for my local developer environment at the Insolvency Service

## Running

Initialise a docker swarm locally

```
docker swarm init
```

Build the stack

```
docker-compose build
```

Deploy the stack to start it

```
docker stack deploy -c docker-compose.yml devenv
```

To tear the stack down and remove it use

```
docker stack rm devenv
```

You can remove the swarm itself with

```
docker swarm leave --force
```

Clear all the containers and images with:

```
docker rm -f $(docker ps -a -q)
docker rmi -f $(docker images -q)
```
