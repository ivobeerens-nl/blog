---
title: "Quick Tip: Disable memory warnings on VMs with NVIDIA GPU profiles"
date: "2020-07-07T05:58:27.000Z"
---

When using PCI passthrough devices such as for example NVIDIA GPUs with VMware vSphere and configure the VMs with a GPU profile, the full memory is reserved (100% Memory Active). When the VM is active, a red "Virtual Machine memory usage" alarm is displayed in the vCenter for every VM.

[![](images/VM-memory-Usage-300x37.png)](https://www.ivobeerens.nl/wp-content/uploads/2020/07/VM-memory-Usage.png)

I see this behavior in a lot of  VDI environments with PCI passthrough GPU cards. Customers I work for ask me to disable this annoying alarm. This can be easily done in the vSphere Client by disabling the "Virtual machine memory usage" alarm:

[![](images/2-300x120.png)](https://www.ivobeerens.nl/wp-content/uploads/2020/07/2.png)

 

When using PowerCLI this can be done with the following command:

\[code language="powershell"\] Get-AlarmDefinition -Name 'Virtual machine memory usage' | Set-AlarmDefinition -Enabled:$false \[/code\]
