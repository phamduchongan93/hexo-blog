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



