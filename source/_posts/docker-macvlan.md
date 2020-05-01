---
title: Docker macvlan Interface
tags: docker
date: 2020-05-01 19:48:03
---


# Build the first interface 

```
docker network create -d macvlan --subnet=192.168.99.0/24 --ip-range=192.168.99.192/26 \
--gateway=192.168.99.1 -o macvlan_mode=bridge -o parent=wlan0 macvlantest
```

# Run the first container to test the interface   
`docker run --net=macvlantest -it alpine /bin/sh`

Then, run the following command to check if the new container interface created by typing:
`ip a s` 

We expect to see the follwing output:

```
/ # ip a s
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
23: eth0@if3: <BROADCAST,MULTICAST,UP,LOWER_UP,M-DOWN> mtu 1500 qdisc noqueue state UP
    link/ether 02:42:c0:a8:63:c0 brd ff:ff:ff:ff:ff:ff
    inet 192.168.99.192/24 brd 192.168.99.255 scope global eth0
       valid_lft forever preferred_lft forever
```

As you can see, the **eth@if3** is succesfully created. 

# Build the second inteface

```
docker network create -d macvlan --subnet=192.168.1.0/24 --ip-range=192.168.1.192/24 \
--gateway=192.168.1.1 -o macvlan_mode=bridge -o parant=wlan1 macvlantest2
# connect to the container
docker network connect macvlantest2 interface-test
``` 

- Now, recheck the running container.

```
pi@rpi4:~ $ docker ps                                                                        
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
e1ffa260c048        alpine              "/bin/sh"           6 minutes ago       Up 6 minutes                            interface-test
```

If your container is running, your can log inside and check out the interfaces

```
docker exec -it e1ffa260c048 /bin/sh
ip a s
```

Expected output: 
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN qlen 1000                
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
25: eth0@if3: <BROADCAST,MULTICAST,UP,LOWER_UP,M-DOWN> mtu 1500 qdisc noqueue state UP 
    link/ether 02:42:c0:a8:63:c0 brd ff:ff:ff:ff:ff:ff
    inet 192.168.99.192/24 brd 192.168.99.255 scope global eth0
       valid_lft forever preferred_lft forever
26: eth1@if9: <NO-CARRIER,BROADCAST,MULTICAST,UP,M-DOWN> mtu 1500 qdisc noqueue state LOWERLAYERDOWN 
    link/ether 02:42:c0:a8:01:02 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.2/24 brd 192.168.1.255 scope global eth1
       valid_lft forever preferred_lft forever
```
