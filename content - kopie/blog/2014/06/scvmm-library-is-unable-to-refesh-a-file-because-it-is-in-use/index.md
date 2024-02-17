---
title: "SCVMM library is unable to refesh a file because it is in use"
date: "2014-06-09T14:53:16.000Z"
categories: 
  - "hyper-v"
  - "scvmm"
tags: 
  - "hyper-v-2"
  - "scvmm"
---

In the jobs window in the System Center Virtual Machine Manager (SCVMM) console , the following warning appeared:

<table cellspacing="0" cellpadding="2" width="744" border="0"><tbody><tr><td valign="top" width="742"><p><font size="2" face="Courier New">Warning (10803)<br>Unable to refresh </font><a href="file://\\server\share\ISO\Windows2012"></a><a href="file://\\server\share\ISO\Windows2012&nbsp;R2\SW_DVD5_Windows_Svr_Std_and_DataCtr_2012_R2_64Bit_English_Core_MLF_X19-05182.ISO"><font size="2" face="Courier New">\\server\share\ISO\Windows2012</font></a><font size="2"><font face="Courier New"> R2\SW_DVD5_Windows_Svr_Std_and_DataCtr_2012_R2_64Bit_English_Core_MLF_X19-05182.ISO because the file is in use by another process.</font></font></p><p><font size="2" face="Courier New">Recommended Action<br>Wait for the next automatic library refresh, or manually refresh the library share after the process completes.</font></p><p><a href="https://www.ivobeerens.nl/wp-content/uploads/2014/06/image.png"><img title="image" style="border-left-width: 0px; border-right-width: 0px; border-bottom-width: 0px; display: inline; border-top-width: 0px" border="0" alt="image" src="images/image_thumb.png" width="727" height="284"></a></p></td></tr></tbody></table>

The warning means that the ISO file is in use by one or more VM’s. To find the VM’s that are using the ISO file I created the following PowerShell script:

Import-module VirtualMachineManager
Get-SCVMMServer -ComputerName VMMSERVER
Get-SCVirtualMachine | Get-SCVirtualDVDDrive | Where-Object {$\_.Connection -eq "ISOImage"} | Select Name, Connection, ISO

The script displays all the VMs that have an ISO file attached. The script is tested against a SCVMM 2012 R2 server.

[![image](images/image_thumb1.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2014/06/image1.png)

After changing the VMs Virtual DVD drive to “No media” the hourly (default) refresh of the library went without a warning.

[![image](images/image_thumb2.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2014/06/image2.png)
