---
author: Ivo Beerens
categories:
- Hyper-V
- Powershell
- scvmm
date: "2013-09-17T15:39:07Z"
guid: http://www.ivobeerens.nl/?p=2430
id: 2430
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
- Powershell
- scvmm
title: Hyper-V Get Snapshot checkpoint file sizes on Cluster Shared Volumes with PowerShell
url: /2013/09/17/list-hyper-v-snapshot-file-sizes-on-cluster-shared-volumes-with-powershell/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

During a Windows Server 2012 Hyper-V Health Check I needed to know the snapshot file sizes for the all the snapshots on the Clustered Shared Volumes (CSVs). The <span style="font-family: 'Times New Roman';">Get-VMCheckpoint</span> Cmdlet does not report the snapshot size. So I create a PowerShell one-liner that displays the following information:

- Location of the snapshot file
- Date and time that the snapshot file was created
- Last write access time of the snapshot file
- File size in MBs

The PowerShell one-liner is executed from a Hyper-V 2012 host that has access to all the Cluster Shared Volumes (CSVs).  
```powershell
Get-ChildItem C:\\ClusterStorage\\ \* -include \*.avhd -recurse | Select-Object Fullname,CreationTime,LastWriteTime,@{"Name"="Size (MB)"; "Expression"={\[int\]($\_.Length/1mb)}} | Out-GridView  
```  
This PowerShell one-liner produces the following output:  
[![image](http://localhost/wp-content/uploads/2013/09/image_thumb.png "image")](http://localhost/wp-content/uploads/2013/09/image.png)
