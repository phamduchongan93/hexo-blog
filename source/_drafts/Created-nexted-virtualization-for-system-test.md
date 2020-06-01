---
title: Created a nested Virtualization for System Testing
tags: [kvm, virtualization]
---

# Getting Started
1. Check for compatibility

  cat /sys/module/kvm_intel/parameters/nested
  Y

2. Enabling the nested feature on boot
  
  vim /etc/modprove.d/kvm.conf

		
