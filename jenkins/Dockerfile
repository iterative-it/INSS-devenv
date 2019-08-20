FROM jenkins/jenkins:lts

RUN apt-get update && apt-get install -y apt-transport-https ca-certificates curl gnupg2 software-properties-common

# Install docker cle
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
RUN apt-get update && apt-get install -y docker-ce-cli

# Install docker-compose
# RUN apt-get update && apt-get install -y py-pip python-dev libffi-dev openssl-dev gcc libc-dev make
RUN curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose
