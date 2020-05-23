---
title: Autostart docker container
tags:
---


## Method 1: Writing systemd startup file

[Unit]
Description: 
Requires=docker.service
After=docker.service

 
``` bash 
  
```
