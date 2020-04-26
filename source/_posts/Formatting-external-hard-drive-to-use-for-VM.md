---
title: Formatting external hard drive to use for VM
date: 2020-04-24 03:30:15
tags: Linux Block-device
---

# Formating XFS 

Component:
 - dump2efs for information
 - xfs_fsr to defrag
 - xfs_freeze to freeze the filesystem


In short, if I want to use the hard drive for incremetal backup, I will pick XFS for my hard drive.

# Formating ZFS 

Component:
 - pooled storage
 - copy-on-write feature
 - Snapshots
 - RAID

If I want to use the hard drive for on going read and write operation as well as running VM, ZFS would be the exellence choice. In fact, in the future, I can add more disks to a storage pooling, allowing me to provie the scalability for my system. 




# Setting up the storage pool in Virsh Envirenment


What will include:
 - Create an directory storage pool named 'storage_pool2'
 - The storges pool with be on a directory. 

1. Locate where the disk is mounted. In my case, I know it's at
```
/home/anpham/storage_pool2/external-disk-vm
```
2. Use virsh to create a directory-based storage pool. 

```
virsh pool-define-as storage_pool2  dir - - - - "/home/anpham/storage_pool2/external-disk-vm"
```

3. Checking and verifying to see if the new pool works
 - `virsh pool-start storage_pool2` to make the pool active.
 - `virsh pool-autostart storage_pool2` to autostart the pool.
 - `virsh pool-list` to view the specs of the pools.
