---
author: Ivo Beerens
categories:
- Uncategorized
date: "2020-07-07T07:58:27Z"
guid: https://www.ivobeerens.nl/?p=7506
id: 7506
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_reddit_counts:
- "2"
ssb_total_counts:
- "2"
title: 'Quick Tip: Disable memory warnings on VMs with NVIDIA GPU profiles'
url: /2020/07/07/quick-tip-disable-memory-warnings-on-vms-with-nvidia-gpu-profiles/
---

When using PCI passthrough devices such as for example NVIDIA GPUs with VMware vSphere and configure the VMs with a GPU profile, the full memory is reserved (100% Memory Active). When the VM is active, a red “Virtual Machine memory usage” alarm is displayed in the vCenter for every VM.

[![](http://localhost/wp-content/uploads/2020/07/VM-memory-Usage-300x37.png)](http://localhost/wp-content/uploads/2020/07/VM-memory-Usage.png)

I see this behavior in a lot of VDI environments with PCI passthrough GPU cards. Customers I work for ask me to disable this annoying alarm. This can be easily done in the vSphere Client by disabling the “Virtual machine memory usage” alarm:

[![](http://localhost/wp-content/uploads/2020/07/2-300x120.png)](http://localhost/wp-content/uploads/2020/07/2.png)

When using PowerCLI this can be done with the following command:

```powershell  
Get-AlarmDefinition -Name ‘Virtual machine memory usage’ | Set-AlarmDefinition -Enabled:$false  
```
