---
title: "Manage Hyper-V in a workgroup remotely"
date: "2015-08-28T07:14:29.000Z"
categories: 
  - "hyper-v"
tags: 
  - "hyper-v-2"
  - "remote"
  - "remotely"
  - "windows-server-2016"
  - "workgroup"
author: Ivo Beerens
---

- Client with Hyper-V Manager (Windows 10). This client is called **win10-01**
- Server with Windows Server 2016 core version with the Hyper-V role enabled. The server is called **hv-02**
- Both systems are in the same workgroup called "workgroup"
- Both systems have the same username and password.

**Configuration on the Windows Server 2016  server**:

- Enable Remote Management

\[code language="PowerShell"\] Configure-SMRemoting.exe -Enable \[/code\]

- Open firewall for  Remote Computer Management

\[code language="PowerShell"\] Set-NetFirewallRule -DisplayGroup 'Windows Management Instrumentation (WMI)' -Enabled true -PassThru Set-NetFirewallRule -DisplayGroup 'Remote Event Log Management' -Enabled true -PassThru \[/code\]

- Open firewall for ping (ICMPv4)

\[code language="PowerShell"\] Set-NetFirewallRule -DisplayName “File and Printer Sharing (Echo Request – ICMPv4-In)” -Enabled True -PassThru \[/code\]

- Enable Remote Desktop and allow remote connections

\[code language="PowerShell"\] cscript.exe c:\\Windows\\System32\\SCregEdit.wsf /AR 0 \[/code\]

- Enable Remote disk management

\[code language="PowerShell"\] Set-NetFirewallRule -DisplayGroup 'Remote Volume Management' -Enabled true -PassThru \[/code\]

 

**Configuration on the Windows 10 client:**

- Create a host file with IP address and hostname of the server. Make sure you can ping the hostname

[![6](images/61-300x151.png)](images/61.png)

- Make sure that the network type is part of a private network before executing the WINRM command

[![1](images/11-300x219.png)](images/11.png) [![2](images/21-300x237.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/08/21.png)

- Enable Remote Management

\[code language="PowerShell"\] winrm quickconfig \[/code\]

- For Managing remote systems

\[code language="PowerShell"\] winrm set winrm/config/client @{TrustedHosts="Name of the Server"} \[/code\]

- Enable remote disk Management (add this command on both systems) firewall rule

\[code language="PowerShell"\] Set-NetFirewallRule -DisplayGroup 'Remote Volume Management' -Enabled true -PassThru \[/code\]

- Open c:\\windows\\system32\\dcomcnfg.exe and allow 'anonymous logon' for local and remote access.

[![5](images/51-300x211.png)](images/51.png)

After making this settings I was able to manage the Windows Server 2016 server with the following tools remotely:

- Hyper-V manager
- Computer Management
- Disk Management

 

[![3](images/31-300x112.png)](images/31.png) [![4](images/41-300x204.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/08/41.png)



