---
title: Create an User with Password and Home Directory
tags: [ Linux ]
---

## Add user with a group and a home directory
```bash
  useradd -m <User_name> -G sudo
  useradd -p <encrypted_password> <User_Name>
```

## Add user with password

```bash
  useradd -p $(openssl passwd -1 $PASS) $USER  
```

