---
author: Ivo Beerens
categories:
- Hyper-V
- scvmm
date: "2014-06-09T16:53:16Z"
guid: http://www.ivobeerens.nl/?p=2826
id: 2826
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- hyper-v
- scvmm
title: SCVMM library is unable to refesh a file because it is in use
url: /2014/06/09/scvmm-library-is-unable-to-refesh-a-file-because-it-is-in-use/
---

In the jobs window in the System Center Virtual Machine Manager (SCVMM) console , the following warning appeared:

| <font face="Courier New" size="2">Warning (10803)    Unable to refresh </font>[](file://\\server\share\ISO\Windows2012)[<font face="Courier New" size="2">\\\\server\\share\\ISO\\Windows2012</font>](file://\\server\share\ISO\Windows2012 R2\SW_DVD5_Windows_Svr_Std_and_DataCtr_2012_R2_64Bit_English_Core_MLF_X19-05182.ISO)<font size="2"><font face="Courier New"> R2\\SW\_DVD5\_Windows\_Svr\_Std\_and\_DataCtr\_2012\_R2\_64Bit\_English\_Core\_MLF\_X19-05182.ISO because the file is in use by another process. </font></font>  <font face="Courier New" size="2">Recommended Action    Wait for the next automatic library refresh, or manually refresh the library share after the process completes.</font>  [![image](http://localhost/wp-content/uploads/2014/06/image_thumb.png "image")](http://localhost/wp-content/uploads/2014/06/image.png) |
|---|

The warning means that the ISO file is in use by one or more VM’s. To find the VM’s that are using the ISO file I created the following PowerShell script:

```
<pre lang="plain">Import-module VirtualMachineManager
Get-SCVMMServer -ComputerName VMMSERVER
Get-SCVirtualMachine | Get-SCVirtualDVDDrive | Where-Object {$_.Connection -eq "ISOImage"} | Select Name, Connection, ISO
```

The script displays all the VMs that have an ISO file attached. The script is tested against a SCVMM 2012 R2 server.

[![image](http://localhost/wp-content/uploads/2014/06/image_thumb1.png "image")](http://localhost/wp-content/uploads/2014/06/image1.png)

After changing the VMs Virtual DVD drive to “No media” the hourly (default) refresh of the library went without a warning.

[![image](http://localhost/wp-content/uploads/2014/06/image_thumb2.png "image")](http://localhost/wp-content/uploads/2014/06/image2.png)
