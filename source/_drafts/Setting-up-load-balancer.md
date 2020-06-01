---
title: Setting up load balancer
tags: [docker,linux]
---

# Setting up the Dockerfile

version: '3.2'
services:
  weather-app1:
    build: ./weather-app
    tty: true
    network:
     - frontend
		weather-app1:
				build: ./weather-app
				tty: true
						network:
						- frontend
		weather-app1:
				build: ./weather-app
				tty: true
				network:
						- frontend
		loadbalancer:
				build: ./load-balancer
				tty: true
				ports:
					- 80:80

networks:
   - frontend
