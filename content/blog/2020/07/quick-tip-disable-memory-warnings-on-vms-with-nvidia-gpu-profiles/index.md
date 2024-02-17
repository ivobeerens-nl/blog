---
title: "Quick Tip: Disable memory warnings on VMs with NVIDIA GPU profiles"
date: "2020-07-07T05:58:27.000Z"
author: Ivo Beerens
---

[![](images/VM-memory-Usage-300x37.png)](images/VM-memory-Usage.png)

I see this behavior in a lot of  VDI environments with PCI passthrough GPU cards. Customers I work for ask me to disable this annoying alarm. This can be easily done in the vSphere Client by disabling the "Virtual machine memory usage" alarm:

[![](images/2-300x120.png)](images/2.png)

 

When using PowerCLI this can be done with the following command:

\[code language="PowerShell"\] Get-AlarmDefinition -Name 'Virtual machine memory usage' | Set-AlarmDefinition -Enabled:$false \[/code\]



