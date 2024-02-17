---
title: "Hyper-V Get Snapshot checkpoint file sizes on Cluster Shared Volumes with PowerShell"
date: "2013-09-17T13:39:07.000Z"
categories: 
  - "hyper-v"
  - "powershell"
  - "scvmm"
tags: 
  - "hyper-v-2"
  - "powershell"
  - "scvmm"
---

During a Windows Server 2012 Hyper-V Health Check I needed to know the snapshot file sizes for the all the snapshots on the Clustered Shared Volumes (CSVs). The Get-VMCheckpoint Cmdlet does not report the snapshot size. So I create a PowerShell one-liner that displays the following information:

- Location of the snapshot file
- Date and time that the snapshot file was created
- Last write access time of the snapshot file
- File size in MBs

The PowerShell one-liner is executed from a Hyper-V 2012 host that has access to all the  Cluster Shared Volumes (CSVs). \[code language="powershell"\]Get-ChildItem C:\\ClusterStorage\\ \* -include \*.avhd -recurse | Select-Object Fullname,CreationTime,LastWriteTime,@{"Name"="Size (MB)"; "Expression"={\[int\]($\_.Length/1mb)}} | Out-GridView \[/code\] This PowerShell one-liner produces the following output: [![image](images/image_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2013/09/image.png)
