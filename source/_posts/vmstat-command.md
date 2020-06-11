---
title: Performance Monitoring in Linux 
tags:
  - lpic2
  - Linux
date: 2020-06-11 02:02:46
---
## Overview
- This is part of lpic2 exam, objective 200.1 - Measure and Troubleshoot Resource Usage. 

## vmstat command

{% codeblock %}
# Display disk statitics
$vmstat -d
nvme0n1  54705  32017 4802359   17720 348189  80080 4514130  276470      0    163
{% endcodeblock %}

## free command
- Concept of memory: cpu can't talk to memory right away, it talks to buffer of the ram first. Buffer access cached for access binary. For example, when a command is executed at the first time, it will be stored in the cache. In the same time, the metadat is stored in buffere.
- When a command is executed, the buffer will be 
- `free -h`, will have the following output.

{% codeblock %}
              total        used        free      shared  buff/cache   available
Mem:            23G        8.4G         11G        373M        3.2G         14G
Swap:           34G          0B         34G

{% endcodeblock %}

{% youtube  Xy_rLc-E4Xg %}

- Explaination:
  - free: is for immediately accessed.
  - buffer: metadata for cache (pointer of memory page).
  - cache: store binary for immediate access. 
  - shared:  

The available will reflect the buffer/cache, shared and free.
- To clear and buffer and cache, we can use the following command.
  - To clear the buffer.
{% codeblock %}
  sync; echo 2 > /proc/sys/vm/drop_caches
{% endcodeblock %}

  - To clear the cache. 
{% codeblock %}
  sync; echo 3 > /proc/sys/vm/drop_caches
{% endcodeblock %}

- 

