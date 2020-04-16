---
title: 'Build IT Automation System - freestyle '
date: 2020-04-08 16:33:56
tags: automation docker ansible 
---

# Intro 

In this article, I will show how quickly you can deploy a stable system for CI/CD. But, the main purpose of this set up is for testing out new docker images. We will issue multiple docker build (`docker build`) via jenkins.  

What we want to achieve:
 - this automation server will be online all the time.
 - generate docker containers for usuage
 - packages and services monitored by ansible 
 - provide reports over a web page 

Infrastructure:
- Jenkin Container (blue occean)
- Port 8080 will be used.
- 

## Install Jenkin Container 

```
# Prebuilt network 
docker network create jenkins

# Pre build volume 
docker volume create jenkins-docker-certs
docker volume create jenkins-data

# Used to run docker inside jenkin container
docker container run --name jenkins-docker --rm --detach \
  --privileged --network jenkins --network-alias docker \
  --env DOCKER_TLS_CERTDIR=/certs \
  --volume jenkins-docker-certs:/certs/client \
  --volume jenkins-data:/var/jenkins_home \
  --volume "$HOME":/home \
  --publish 3000:3000 docker:dind

# Initiate jenkin docker container
docker container run --name jenkins-tutorial --rm --detach \
  --network jenkins --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 \
  --volume jenkins-data:/var/jenkins_home \ 
  --volume jenkins-docker-certs:/certs/client:ro \
  --volume "$HOME":/home \ 
  --publish 8080:8080 jenkinsci/blueocean
```

## Add Ansible on RPI4
 - Set up ssh key for ansible.
 - create playbook for installing jenkins and required package. 

## Create jobs 

