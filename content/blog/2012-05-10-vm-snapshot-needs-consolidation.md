---
author: Ivo Beerens
categories:
- snapshot
- vsphere5
date: "2012-05-10T09:59:18Z"
guid: http://www.ivobeerens.nl/?p=1545
id: 1545
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Snapshot
- vsphere5
title: VM snapshot needs consolidation
url: /2012/05/10/vm-snapshot-needs-consolidation/
---

When a snapshot didn’t commit properly, it can happen that the snapshot manager in the vCenter server shows no snapshot(s), but that there are still active delta files on the datastore. These ‘hidden’ snapshot can cause the datastore to run out of space.

To report these ‘hidden’ snapshots (prior vSphere 5), I created a script that searches all the datastores for ‘\*.delta’ files and reported them by mail.

In vSphere 5 you have a new feature that reports and make it possible to consolidate these ‘hidden’ snapshot(s). In vSphere 5 you get a warning ‘**Virtual machine disks consolidation is needed’** when the virtual machine snapshot consolidation has failed.

[![image](http://localhost/wp-content/uploads/2012/05/image8_thumb.png "image")](http://localhost/wp-content/uploads/2012/05/image81.png)

The snapshot manager shows no snapshots but there are delta files present on the datastore(s).

| [![image](http://localhost/wp-content/uploads/2012/05/image_thumb9.png "image")](http://localhost/wp-content/uploads/2012/05/image9.png) | [![image](http://localhost/wp-content/uploads/2012/05/image_thumb10.png "image")](http://localhost/wp-content/uploads/2012/05/image10.png) |
|---|---|

In the vCenter server on the Virtual Machines tab you can enable the field “Needs Consolidation” to filter all the VMs that needs consolidation.

[![image](http://localhost/wp-content/uploads/2012/05/image12_thumb.png "image")](http://localhost/wp-content/uploads/2012/05/image12.png)

To consolidate the snapshot, right-click the virtual machine and choose **Snapshot** – **Consolidate**.

[![image](http://localhost/wp-content/uploads/2012/05/image20_thumb.png "image")](http://localhost/wp-content/uploads/2012/05/image20.png)

Confirm the consolidate

[![image](http://localhost/wp-content/uploads/2012/05/image24_thumb.png "image")](http://localhost/wp-content/uploads/2012/05/image24.png)

Check the datastore and all the delta files are consolidated

[![image](http://localhost/wp-content/uploads/2012/05/image27_thumb.png "image")](http://localhost/wp-content/uploads/2012/05/image27.png)

With PowerCLI you can use the following one liner to list all the VMs that needs consolidation (thanks to [Luc Dekens](http://www.lucd.info/) ):

```
<pre lang="plain">Get-VM | where {$_.ExtensionData.Runtime.consolidationNeeded} | Select Name 
```

```
<pre lang="plain"> 
```

\[ad#banner\]
