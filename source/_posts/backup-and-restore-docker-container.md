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
