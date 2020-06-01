---
title: Deploy vultr instances with terraform
tags:
  - terrform
  - iac
  - vulr
date: 2020-06-01 12:21:57
---


## Spinning up Cloud Instances

## What needed:
* API key from the Vultr Account.
* SSH public key for remote access.

## Sample of terraform

```
# Configure the vultr provider

provider "vultr" {
  api_key = "provided by vultr server"
  rate_limit = 700
  retry_limit = 3 
}


# creat an ssh key
resource "vultr_ssh_key" "my_ssh_key" {
  name = "ssh-key"
  # normally it would be in ./ssh/id_rsa.pub
  ssh_key = "ssh-rsa <ssh-public-key> anpham@dell-laptop"

}

# Create a web server
resource "vultr_server" "web-nginx" {
  plan_id = "201" 
  region_id = "6"  # atlanta servers
  os_id = "167"  # centos os 
  tag = "made-by-terraform"
  hostname = "web-server"
}

```

