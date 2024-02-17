---
title: "VM snapshot needs consolidation"
date: "2012-05-10T07:59:18.000Z"
categories: 
  - "snapshot-2"
  - "vsphere5"
tags: 
  - "snapshot"
  - "vsphere5"
---

When a snapshot didn’t commit properly, it can happen that the snapshot manager in the vCenter server shows no snapshot(s), but that there are still active delta files on the datastore. These ‘hidden’ snapshot can cause the datastore to run out of space.

To report these ‘hidden’ snapshots (prior vSphere 5), I created a script that searches all the datastores  for ‘\*.delta’ files and reported them by mail.  

In vSphere 5 you have a new feature that reports and make it possible to consolidate these  ‘hidden’ snapshot(s). In vSphere 5 you get  a warning ‘**Virtual machine disks consolidation is needed’** when the virtual machine snapshot consolidation has failed.

[![image](images/image8_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image81.png)

The snapshot manager shows no snapshots but there are delta files present on the datastore(s).

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2012/05/image9.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="images/image_thumb9.png" width="293" height="238"></a></td><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2012/05/image10.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="images/image_thumb10.png" width="392" height="226"></a></td></tr></tbody></table>

In the vCenter server on the Virtual Machines tab you can enable the field “Needs Consolidation” to filter all the VMs that needs consolidation.

[![image](images/image12_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image12.png)

To consolidate the snapshot, right-click the virtual machine and choose **Snapshot** \- **Consolidate**.

[![image](images/image20_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image20.png)

Confirm the consolidate

[![image](images/image24_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image24.png)

Check the datastore and all the delta files are consolidated

[![image](images/image27_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/05/image27.png)

With PowerCLI you can use the following one liner to list all the VMs that needs consolidation (thanks to [Luc Dekens](http://www.lucd.info/) ):

Get-VM | where {$\_.ExtensionData.Runtime.consolidationNeeded} | Select Name 

\[ad#banner\]
