# INSS-devenv
Docker files, scripts and utils for my local developer environment at the Insolvency Service

docker rm -f $(docker ps -a -q)
docker rmi -f $(docker images -q)

docker stack deploy -c docker-compose.yml devenv