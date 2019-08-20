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
docker volume prune
```

docker build -t jenkins/dotnet .
docker run -u root --rm -d -p 8080:8080 -p 50000:50000 -v jenkins-data:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins/dotnet