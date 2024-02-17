---
author: Ivo Beerens
categories:
- VMware
date: "2017-02-15T21:08:18Z"
guid: https://www.ivobeerens.nl/?p=4955
id: 4955
ssb_fbshare_counts:
- "23"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "23"
tags:
- esxi
- VMware
title: Patch VMware ESXi hosts by command line
url: /2017/02/15/patch-vmware-esxi-6-5-hosts-command-line/
---

There a several ways to patch a VMware ESXi server. vSphere Update Manager (VUM) can update for example a complete ESXi host cluster fully automatic. vSphere Update Manager requires a vCenter Server. When you don’t have a vCenter Server patching can be done from the command line.

Here is a quick overview of how to patch an ESXi 6.x or 7.x host to the latest patch or version (from ESXi 6 to 7 for example).

**Step 1**. Download the latest patch bundle from the VMware Web site, [link](https://www.vmware.com/patchmgr/findPatchByReleaseName.portal). VMware ESXi patches are cumulative! Each patch bundle (.zip archive) includes all the updates from prior patches.

[![](http://localhost/wp-content/uploads/2017/02/1-300x111.png)](http://localhost/wp-content/uploads/2017/02/1.png)

**Step 2**. Upload the patch bundle (zip) to a (central) datastore with the vSphere Client (prior vSphere 6.5), vSphere Web Client, ESXi host client.

[![](http://localhost/wp-content/uploads/2017/02/3-300x127.png)](http://localhost/wp-content/uploads/2017/02/3.png)

**Step 3**. Enable SSH

In the vSphere Web client start the SSH service and make a SSH session to the ESXi host

[![](http://localhost/wp-content/uploads/2017/02/4-300x131.png)](http://localhost/wp-content/uploads/2017/02/4.png)

**Step 4.** Put the host in maintenance mode

```powershell  
vim-cmd hostsvc/maintenance\_mode\_enter  
```

**Step 5**. Install the patch bundle

Using esxcli with the install method has the possibility of overwriting existing drivers. If you are using third-party ESXi images, VMware recommends using the **update** method to prevent an unbootable state. The following command will install the patch bunde:

```powershell  
esxcli software vib update -d /vmfs/volumes/datastore/patchbundle.zip  
```

For example install HPE ESXi 6 Update 3:

```powershell  
esxcli software vib update -d /vmfs/volumes/VMFS01/VMware-ESXi-6.0.0-Update3-5050593-HPE-600.9.7.0.17-Feb2017-depot.zip  
```

After the patch bundle is installed check the message. It must say “The update completed successfully, but the system needs to be rebooted for changes to be effective.”

[![](http://localhost/wp-content/uploads/2017/02/2-300x117.png)](http://localhost/wp-content/uploads/2017/02/2.png)

**Step 6**. Reboot the host by entering the following command:

```powershell  
reboot  
```

**Step 7**. Make a SSH session to the ESXi host and exit maintenance mode

```powershell  
vim-cmd hostsvc/maintenance\_mode\_exit  
```
