---
title: Method of Setting Test Environmnet for VM
tags: [virsh, kvm]
---

# Method 1: Creating a Snapshot
* Pros: Cost less storage resources. 
* Cons: Can't stored on secondary block device as backup.

# Method 2: Replicate the vm 
* Pros: Fulll VM that is able to be migrated on a different system. 
* Cons: 
  - Need extra step if the second storage is added.
  - Cost double current VM storage. 


# Method 3: Deploy a dedicate VM via terraform with libvirt as provider (devops approach)
Refer to following guide to prebuilt your system. Be advised, you have install a terraform and libvirt plugin for the system. Although it's not a lengthy process, it may cause some issues on different linux distribution.

![Howto: Provisions vms on kvm with terraform](https://computingforgeeks.com/how-to-provision-vms-on-kvm-with-terraform/)

* Pros: Able to spawning mutiple instances. Can be utilized with gits.
* Cos: Hard to migrate current stable system, especially the configuration.
