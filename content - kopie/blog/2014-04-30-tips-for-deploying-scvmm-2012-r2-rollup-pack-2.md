---
author: Ivo Beerens
categories:
- Hyper-V
- scvmm
- Update
date: "2014-04-30T08:56:20Z"
guid: http://www.ivobeerens.nl/?p=2785
id: 2785
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- scvmm
- update
title: Tips for deploying SCVMM 2012 R2 Rollup 2
url: /2014/04/30/tips-for-deploying-scvmm-2012-r2-rollup-pack-2/
---

Last week Update Rollup 2 (UR2) for System Center 2012 R2 Virtual Machine Manager is released. UR2 contains important fixes for SCVMM2012 R2. Here are some deployment tips for UR2:

- Wait a least couple of weeks before deploying Update Rollups in your production environment. It happens that new Update Rollups contains huge bugs and are pulled back!
- Make sure you have a backup of the SCVMM database before installing UR2
- Install the UR2 by download the VMM management server and VMM admin console packages [link](http://support.microsoft.com/kb/2932926) (or use Windows Update /WSUS to install both packages). Older packages such as UR1 does not need to be removed. In a SCVMM HA environment install UR2 first on the passive node, perform a failover and install UR2 on the other node.

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb9.png "image")](http://localhost/wp-content/uploads/2014/04/image9.png)

- After installing UR2 update execute the SQL script listed in the KB2932926 article on the SCVMM database

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb10.png "image")](http://localhost/wp-content/uploads/2014/04/image12.png)

- In the VMM console check the version by selecting help. The UR2 must be 3.2.7634.0.
- This step is often forgotten. In the VMM admin console perform a cluster refresh (**Fabric-Cluster-Refesh**). After the refresh job completes the host status is changed in “Needs Attention”. This means that the VMM agent must be updated on all the hosts.

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb11.png "image")](http://localhost/wp-content/uploads/2014/04/image13.png)

- Update the VMM agent by right click on the host en choose “Update Agent”. No reboot of the host is required. Using PowerShell the “<span style="font-family: 'Courier New';">Update-VMMManagedComputer</span>” cmdlet can be used to update the agent

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb12.png "image")](http://localhost/wp-content/uploads/2014/04/image15.png)

- After the VMM agent is updated on the host check the version of the agent on the general tab on the host. The UR2 agent version must be 3.2.7634.0.

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb13.png "image")](http://localhost/wp-content/uploads/2014/04/image16.png)

- With PowerShell you can list all the agent versions by using:

```powershell  
Get-VMMMangedComputer | Select Name, AgentVersion  
```

[![image](http://localhost/wp-content/uploads/2014/04/image_thumb14.png "image")](http://localhost/wp-content/uploads/2014/04/image18.png)

**System Center Virtual Machine Manager (SCVMM) 2012 R2 builds and versions**

| **Build** | **Version** |
|---|---|
| 3.2.7510.0 | System Center 2012 R2 Virtual Machine Manager RTM |
| 3.2.7620.0 | Update Rollup 1 (UR1) |
| 3.2.7634.0 | Update Rollup 2 (UR2) |
| 3.2.7672.0 | Update Rollup 3 (UR3) |
| 3.2.7768.0 | Update Rollup 4 (UR4) |
| 3.2.7895.0 | Update Rollup 5 (UR5) |
| 3.2.8002.0 | Update Rollup 6 (UR6) |
| 3.2.8071.0 | Update Rollup 7 (UR7) |
| 3.2.8117.0 | Update Rollup 8 (UR8) |
| 3.2.8145.0 | Update Rollup 9 (UR9) |
| 3.2.8169.0 | Update Rollup 10 (UR10) |
| 3.2.8224.0 | Update Rollup 11 (UR11) |
| 3.2.8228.0 | Update Rollup 11 (Hotfix 1) |
| 3.2.8292.0 | Update Rollup 12 (UR12) |
