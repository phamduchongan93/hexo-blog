---
title: Clean Ubuntu Repository
tags:
  - ubuntu
  - clean
date: 2021-01-23 18:49:50
---


# How to Clean Ubuntu Repository

## Bug or Error 

```
Err http://ppa.launchpad.net natty/main Sources                                   
  404  Not Found
Err http://ppa.launchpad.net natty/main i386 Packages                             
  404  Not Found
```
## Problem
- Repository can't be connected or no longer available.
- Wrong repo info added.

## Solution
- Search for apt sources files .
`ls /etc/apt/sources.list.d`
- remove the unwanted or corrupted file. For instance, the file cause the error is myppa.list. Type the following to remove the file.
`rm -/etc/apt/sources.list.d/corrupted_app.list`
