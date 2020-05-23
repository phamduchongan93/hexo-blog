---
title: Ansbile 
tags: [ ansible ]
---

# Setting the Ansible Inventory 

By default, ansible will use the inventory files located in `/etc/ansible/hosts`

Additionally, you can spectify the target for ansible command with '-i' option. For example:

`ansbile -i <hostfile>  <hostname> -m ping`

This will ping the hosts in the hostfile.

The following is description for the hosts inventory file.

```bash
[treehouses]
192.168.0.10
192.168.0.1
192.168.0.2
192.168.0.3
192.168.0.4
192.168.0.5

[ans]

[digital occean]

[linuxacademy]
phamduchongan932c.mylabserver.com
phamduchongan932d.mylabserver.com 

```
# In Conclusion:

The '-i' will indicate the inventory files, and '-m ping' module will ping the hosts in the inventory files. To change the default inventory configuration, find the `/etc/ansible/ansible.cfg` file and comment out the 'inventory value'.


