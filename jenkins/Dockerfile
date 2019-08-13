FROM jenkins/jenkins:lts

# Switch to root to install .NET Core SDK
USER root

RUN apt-get update && apt-get install -y curl apt-utils apt-transport-https

# Display user and distro for debugging
RUN uname -a && cat /etc/*release

# Install dotnet core 2.2
RUN wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
RUN mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
RUN wget -q https://packages.microsoft.com/config/debian/9/prod.list
RUN mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
RUN chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
RUN chown root:root /etc/apt/sources.list.d/microsoft-prod.list

RUN apt-get update && apt-get install -y dotnet-sdk-2.2

# Install docker-compose
# RUN apt-get update && apt-get install -y py-pip python-dev libffi-dev openssl-dev gcc libc-dev make
RUN curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose

# Switch back to the jenkins user
USER jenkins