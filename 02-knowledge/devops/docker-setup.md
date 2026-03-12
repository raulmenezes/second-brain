---
tags:
  - area/devops
  - area/knowledge
  - topic/angular
  - topic/docker
  - topic/javascript
  - topic/kubernetes
  - topic/networking
  - topic/snippets
---

# Docker Setup

## Get Docker for Mac

https://docs.docker.com/docker-for-mac/install/

## Activate bash completion for Docker

cd /usr/local/etc/bash_completion.d
ln -s /Applications/Docker.app/Contents/Resources/etc/docker.bash-completion
ln -s /Applications/Docker.app/Contents/Resources/etc/docker-machine.bash-completion
ln -s /Applications/Docker.app/Contents/Resources/etc/docker-compose.bash-completion

## Docker useful commands

**Run an nginx Image on port 80** 
*docker run -d -p 80:80 --name webserver nginx*

*docker ps -a*

**Remove Container**
*docker rm -f* 

**Remove Image** 
*docker rmi* 

**SSH into Container**
*docker exec -i -t  bash*

**Reload the NGINX configuration run the command:**
*docker kill -s HUP *

**Restart Docker container**
--restart=always

**Docker Registry API - Catalog**
http://10.33.9.11:5000/v2/_catalog
*curl 10.33.9.11:5000/v2/_catalog*

**List all tags for a repository:**
*curl 10.33.9.11:5000/v2/voice-fe/tags/list*

docker run -it supertest2014/nyan
docker run -d --name firefox -e DISPLAY=192.168.1.74:0 -v /tmp/.X11-unix:/tmp/.X11-unix jess/firefox
docker run --memory 512mb --net host --security-opt seccomp:unconfined -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=192.168.1.74:0 --name chrome jess/chrome

## Node - Dockerfile Example

# Create image based on the official Node 6 image from dockerhub
FROM node:6

# Create a directory where our app will be placed
RUN mkdir -p /usr/src/app

# Change directory so that our commands run inside this new directory
WORKDIR /usr/src/app

# Copy dependency definitions
COPY package.json /usr/src/app

# Install dependecies
RUN npm install

# Get all the code needed to run the app
COPY . /usr/src/app

# Expose the port the app runs in
EXPOSE 4200

# Serve the app
CMD \["npm", "start"\]

**Nginx - Dockerfile Example**

## FROM nginx

## COPY dist /usr/share/nginx/html

## EXPOSE 80

**Build Docker** 

-f argument to docker build to specify the name of the Dockerfile to use:

*docker build -t : *

**Example**
*docker build -t angular-client:dev .*
*docker build -t voice:dev .*

*docker build* -f Dockerfile-frontend *-t voice:dev .* 

docker build --build-arg env=${ENV_NAME} -f Dockerfile-frontend -t voice:dev . 

docker run -d --name  -p   

*docker run -d --name angular-client -p 4200:4200 angular-client:dev*
*docker run -d --name voice -p 4200:4200 voice:dev*
*docker run --env env=raul --name voice -p 4200:4200 -v $(pwd):/usr/src/app voice:dev*

--env =

## Get Gcloud

Follow installation setup from https://cloud.google.com/sdk/docs/

# Kubernetes Setup

## **Kubectl Completion command**
*source <(kubectl completion bash)*

## Related
- [[devops-moc]]
- [[docker]]
- [[what-is-docker]]
- [[overview-kibernetes]]
