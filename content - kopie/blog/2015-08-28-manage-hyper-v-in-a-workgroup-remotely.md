---
author: Ivo Beerens
categories:
- Hyper-V
date: "2015-08-28T09:14:29Z"
guid: http://www.ivobeerens.nl/?p=3963
id: 3963
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- hyper-v
- remote
- remotely
- windows server 2016
- workgroup
title: Manage Hyper-V in a workgroup remotely
url: /2015/08/28/manage-hyper-v-in-a-workgroup-remotely/
---

Managing Hyper-V remotely in a workgroup can be challenging to configure. This is still the case for Windows Server 2016. For a testing environment I needed to remotely manage Windows Server 2016 core server with the Hyper-V role enabled from Windows 10 with the Hyper-V manager. I used the following manual configuration:

- Client with Hyper-V Manager (Windows 10). This client is called **win10-01**
- Server with Windows Server 2016 core version with the Hyper-V role enabled. The server is called **hv-02**
- Both systems are in the same workgroup called “workgroup”
- Both systems have the same username and password.

**Configuration on the Windows Server 2016 server**:

- Enable Remote Management

```powershell  
Configure-SMRemoting.exe -Enable  
```

- Open firewall for Remote Computer Management

```powershell  
Set-NetFirewallRule -DisplayGroup ‘Windows Management Instrumentation (WMI)’ -Enabled true -PassThru  
Set-NetFirewallRule -DisplayGroup ‘Remote Event Log Management’ -Enabled true -PassThru  
```

- Open firewall for ping (ICMPv4)

```powershell  
Set-NetFirewallRule -DisplayName “File and Printer Sharing (Echo Request – ICMPv4-In)” -Enabled True -PassThru  
```

- Enable Remote Desktop and allow remote connections

```powershell  
cscript.exe c:\\Windows\\System32\\SCregEdit.wsf /AR 0  
```

- Enable Remote disk management

```powershell  
Set-NetFirewallRule -DisplayGroup ‘Remote Volume Management’ -Enabled true -PassThru  
```

**Configuration on the Windows 10 client:**

- Create a host file with IP address and hostname of the server. Make sure you can ping the hostname

[![6](http://localhost/wp-content/uploads/2015/08/61-300x151.png)](http://localhost/wp-content/uploads/2015/08/61.png)

- Make sure that the network type is part of a private network before executing the WINRM command

[![1](http://localhost/wp-content/uploads/2015/08/11-300x219.png)](http://localhost/wp-content/uploads/2015/08/11.png) [![2](http://localhost/wp-content/uploads/2015/08/21-300x237.png)](http://localhost/wp-content/uploads/2015/08/21.png)

- Enable Remote Management

```powershell  
winrm quickconfig  
```

- For Managing remote systems

```powershell  
winrm set winrm/config/client @{TrustedHosts="Name of the Server"}  
```

- Enable remote disk Management (add this command on both systems) firewall rule

```powershell  
Set-NetFirewallRule -DisplayGroup ‘Remote Volume Management’ -Enabled true -PassThru  
```

- Open c:\\windows\\system32\\dcomcnfg.exe and allow ‘anonymous logon’ for local and remote access.

[![5](http://localhost/wp-content/uploads/2015/08/51-300x211.png)](http://localhost/wp-content/uploads/2015/08/51.png)

After making this settings I was able to manage the Windows Server 2016 server with the following tools remotely:

- Hyper-V manager
- Computer Management
- Disk Management

[![3](http://localhost/wp-content/uploads/2015/08/31-300x112.png)](http://localhost/wp-content/uploads/2015/08/31.png) [![4](http://localhost/wp-content/uploads/2015/08/41-300x204.png)](http://localhost/wp-content/uploads/2015/08/41.png)
