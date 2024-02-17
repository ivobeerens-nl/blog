---
title: "Fix orphaned vSAN objects"
date: "2017-03-21T09:00:20.000Z"
categories: 
  - "vmware"
tags: 
  - "vmware"
  - "vsan"
---

In the vSphere Web client an orphaned  vSAN object was listed named:

\[code language="text"\] /vmfs/volume/vsanuuid \[/code\]

[![](images/1-300x28.png)](https://www.ivobeerens.nl/wp-content/uploads/2017/03/1.png)

From the vSphere Web Client you cannot manage orphaned vSAN objects . To check and fix orphaned vSAN objects, the Ruby vSphere Console (RVC) is needed.  The 'vsan.check\_state' command checks if VMs and Virtual SAN objects are valid and accessible.

After logging in the RVC (rvc administrator@vsphere.local@localhost), execute the "vsan.check\_state -r" command at the cluster level:

\[code language="text"\] /localhost/dc-beerens-01/computers/CL-01/vsan.check\_state -r \[/code\]

The "-r" parameter refreshes the VMX and registers the VMs.

[![](images/2-300x170.jpg)](https://www.ivobeerens.nl/wp-content/uploads/2017/03/2.jpg)

After running the "vsan.check\_state -r" command, the vSAN object is listed as VM back again in the vSphere Web Client.
