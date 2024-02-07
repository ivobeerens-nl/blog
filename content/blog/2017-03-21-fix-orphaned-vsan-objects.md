---
author: Ivo Beerens
categories:
- VMware
date: "2017-03-21T10:00:20Z"
guid: https://www.ivobeerens.nl/?p=5019
id: 5019
ssb_fbshare_counts:
- "11"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "11"
tags:
- VMware
- VSAN
title: Fix orphaned vSAN objects
url: /2017/03/21/fix-orphaned-vsan-objects/
---

In the vSphere Web client an orphaned vSAN object was listed named:

\[code language=”text”\]  
/vmfs/volume/vsanuuid  
```

[![](http://localhost/wp-content/uploads/2017/03/1-300x28.png)](http://localhost/wp-content/uploads/2017/03/1.png)

From the vSphere Web Client you cannot manage orphaned vSAN objects . To check and fix orphaned vSAN objects, the Ruby vSphere Console (RVC) is needed. The ‘vsan.check\_state’ command checks if VMs and Virtual SAN objects are valid and accessible.

After logging in the RVC (rvc administrator@vsphere.local@localhost), execute the “vsan.check\_state -r” command at the cluster level:

\[code language=”text”\]  
/localhost/dc-beerens-01/computers/CL-01/vsan.check\_state -r  
```

The “-r” parameter refreshes the VMX and registers the VMs.

[![](http://localhost/wp-content/uploads/2017/03/2-300x170.jpg)](http://localhost/wp-content/uploads/2017/03/2.jpg)

After running the “vsan.check\_state -r” command, the vSAN object is listed as VM back again in the vSphere Web Client.
