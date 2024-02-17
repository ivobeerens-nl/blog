---
author: Ivo Beerens
categories:
- azure
- Uncategorized
date: "2023-02-01T12:55:44Z"
guid: https://www.ivobeerens.nl/?p=8606
id: 8606
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- Azure
title: 'Quick tip: Reset the password of an Azure Virtual Machine'
url: /2023/02/01/quick-tip-reset-the-password-of-a-azure-virtual-machine/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

In my Azure test tenant, I forgot the password of an Azure Windows Domain Controller VM. In Azure, there is a Reset Password option available in the VM options.

[![](http://localhost/wp-content/uploads/2023/02/PasswordResetFailed-300x115.jpg)](http://localhost/wp-content/uploads/2023/02/PasswordResetFailed.jpg)

The password reset update failed. The password reset option uses a VM Access extension. When digging into the activity log I found the following error:

> VMAccess Extension does not support Domain Controller

So I went to another approach using the following steps:

**Prerequisites:**

- Ensure the VM status is running
- Create a new password 
    - Portal – between 12 – 123 characters
    - PowerShell – between 8 – 123 characters
    - CLI – between 12 – 123
    - Have lower characters
    - Have upper characters
    - Have a digit
    - Have a special character (Regex match \[\\W\_\])

## Using the Azure portal

- - Log in to the Azure portal
    - Navigate to the Virtual Machine that you want to reset the password for.
    - Select the Virtual Machine
    - Select Run Command
    - Select RunPowerShellScript
    - In the “Run Command Script” window enter:

\[code language=”text”\]  
net user <username> <password>  
```

[![](http://localhost/wp-content/uploads/2023/01/0-300x104.jpg)](http://localhost/wp-content/uploads/2023/01/0.jpg)

## Using Cloud Shell

- Log in to the Azure portal
- In the Azure Portal open Cloud Shell
- Select Bash
- In the following command change: <vm> <resource group the vm belongs > <username> and <password>

\[code language=”text”\]  
az vm run-command invoke –command-id RunPowerShellScript –name <vm> -g <resource group the VM belongs too> –scripts "net user <username> <password>"  
```

[![](http://localhost/wp-content/uploads/2023/02/1-300x104.jpg)](http://localhost/wp-content/uploads/2023/02/1.jpg)

Using the RunPowerShellScript is a lifesaver when you forgot the password of a Windows Domain Controller VM in Azure. This procedure works also for regular Windows VMs.
