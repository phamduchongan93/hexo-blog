---
title: Netplan Guide
tags:
  - linux
  - ubuntu
date: 2020-06-10 00:48:54
---
# Sample of Editing Netplan

## For ethernet
## For wifi
- Create a file in `/etc/netplan`
  - Set up the wifi with dhcp

{% codeblock %}
network:
  version: 2
  renderer: networkd
  wifis:
    wlp2s0:
      nameservers:
        addresses: 
          - 8.8.8.8
          - 8.8.4.4
      access-points:
        "AP_Name":
          password: "wifi_pass"
      dhcp4: true 
{% endcodeblock %}

- Set up the wifi with static IP 

{% codeblock %}
network:
  version: 2
  renderer: networkd
  wifis:
    wlp2s0:
      dhcp4: no
 					addresses: [192.168.1.100/24]
  '  ''  ''  ''  'gateway4: 192.168.1.1
	 				nameservers:
								addresses: [192.168.1.1,8.8.8.8]
					 access-points:
	 						"accespoint_name":
											password: "your_pass"
{% endcodeblock %}

- Finally, type `netplan generate && netplan apply` to apply the configuration.

#References:
- Real time demo link: 
{% youtube eTqtl169oSY%}

