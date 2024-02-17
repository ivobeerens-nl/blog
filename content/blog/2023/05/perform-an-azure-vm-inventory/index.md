---
title: "Perform an Azure Virtual Machine (VM) inventory with PowerShell"
date: "2023-05-16T17:48:07.000Z"
categories: 
  - "azure"
tags: 
  - "azure"
  - "microsoft"
author: Ivo Beerens
---

![](images/1-1024x143.jpg)

The following VM information is displayed per subscription:

- `Name`
- `PowerState`
- `Region`
- `Resource Group`
- `VM Size`
- `CPU Cores`
- `Memory (MB)`
- `License Type`
- `Operating System`
- `Offer`
- `SKU`
- `Publisher`
- `VM Generation`
- `VM Agent version`
- `OS Name`
- `OS Version`
- `NIC Name`
- `VNet`
- `Private IP address`
- `Public IP address`
- `OS disk name`
- `OS disk size (GB)`
- `OS storage type`
- `OS disk caching`
- `Data disks count`
- `Data disks names`
- `Admin username`
- `If boot diagnostics is enabled`
- `Boot diagnostics storage account`
- `Tags`
- `The time the VM was created`

The output will be displayed in the PowerShell console, to a PowerShell GridView output, and saved to a delimited CSV file. The "**azurevm-inventory.ps1**" script can be found on my GitHub repo, [link](https://github.com/ibeerens/Azure).



