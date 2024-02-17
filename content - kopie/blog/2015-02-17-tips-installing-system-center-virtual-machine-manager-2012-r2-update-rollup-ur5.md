---
author: Ivo Beerens
categories:
- Hyper-V
- scvmm
date: "2015-02-17T19:53:53Z"
guid: http://www.ivobeerens.nl/?p=3416
id: 3416
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- hyper-v
- scvmm
title: Tips for installing System Center Virtual Machine Manager 2012 R2 Update Rollup
  (UR5)
url: /2015/02/17/tips-installing-system-center-virtual-machine-manager-2012-r2-update-rollup-ur5/
---

Here are some tips for installing System Center 2012 R2 Virtual Machine Manager Update Rollup (UR5):

- UR5 is available from Microsoft Update or by manual download. If you are not installing UR5 through Microsoft Update (e.g. you’re downloading the update and then installing it), you must install using elevated privileges. If you do not do this the update may fail silently.
- During the UR5 installion the System Center Virtual Machine Manager &amp; Agent will be stopped
- [![3](http://localhost/wp-content/uploads/2015/02/3-300x267.png)](http://localhost/wp-content/uploads/2015/02/3.png)
- After the SCVMM UR5 server component, reboot the VMM server before installing the UR5 console
- Before Update Rollup 5, you had to manually update the System Center Virtual Machine Manager DHCP Server (x64) component. As of Update Rollup 5, this is no longer required. When updating the agent on the server the DHCP server components is updated too.
- [![Agents DHCP](http://localhost/wp-content/uploads/2015/02/Agents-DHCP-300x60.png)](http://localhost/wp-content/uploads/2015/02/Agents-DHCP.png)
- The new SCVMM UR5 agent build version is: **3.2.7895.0**
- The Microsoft System Center Virtual Machine Manager DHCP Server (x64) build version is still **3.2.7768.0**
- Make sure to update the agent on all the infrastructure servers such as the Update Server and library server. In VMM click on Fabric- Server for a complete overview
- [![Updateagent](http://localhost/wp-content/uploads/2015/02/Updateagent-300x142.png)](http://localhost/wp-content/uploads/2015/02/Updateagent.png)
- Refresh the cluster after updating the agents
- When starting the VMM console the following error appears:
- [![pipeline error](http://localhost/wp-content/uploads/2015/02/pipeline-error-300x201.png)](http://localhost/wp-content/uploads/2015/02/pipeline-error.png)
- This error is permission related. To solve this error add the “Authenticated Users” group to the AddInPipeline directory and assign read and execute rights. The installation of VMM can be found under: <Driveletter>:\\Program Files\\Microsoft System Center 2012 R2\\Virtual Machine Manager\\bin\\AddInPipeline.
- **Update 24-02-2015**: Microsoft released a hotfix for UR5 that addresses replica and smb shares issues. The link to the KB can be found here, [link](http://support2.microsoft.com/kb/3039296/en-us).



For all the details on SCVMM 2012 R2 UR5, see the following:

- KB3023195 – Description of the security update for Update Rollup 5 for System Center 2012 R2 Virtual Machine Manager, [link](http://support.microsoft.com/kb/3023195)
