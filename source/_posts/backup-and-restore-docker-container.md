---
title: Backup and Restore Docker Container
date: 2020-04-07 23:24:00
tags: [ docker ]
---

## Find the container id

```
 docker ps
```

## Save current working container

```
 docker commit -p [container-id] new-name
 docker save -o <new-name>.tar <new-name>
```

## Load the saved file on new device

```
 docker load -i <new-name>.tar
```

## Optional
* You can send the container over the cloud by following command

```
  scp -v <new-namr>.tar root@<remote-server>:<directory_to_store> 
```
## Remove the backup from the server 
Find the image and erase it with `docker rmi` command 

```
  docker images -a
  docker rmi <new-name>
```
