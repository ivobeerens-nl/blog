---
author: Ivo Beerens
categories:
- ESXi
- snapshot
date: "2012-04-20T10:45:42Z"
guid: http://www.ivobeerens.nl/?p=1495
id: 1495
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- esxi
- Snapshot
title: VMware ESXi 5 snapshot changes
url: /2012/04/20/vmware-esxi-5-snapshot-changes/
---

In ESX(i) 3.x and 4.x snapshots files are default created in the virtual machine’s working directory (home directory). The working directory is the same directory as the were the virtual machine configuration (\*.vmx) file is stored.

[![snapshot-working basic esxi4](http://localhost/wp-content/uploads/2012/04/snapshot-working-basic-esxi4_thumb1.jpg "snapshot-working basic esxi4")](http://localhost/wp-content/uploads/2012/04/snapshot-working-basic-esxi41.jpg)

In this example a VM called “test” that has two disks (VMDK’s) placed on two datastores. The first disk is created on the VMFS01 datastore and the second disk is created on the VMFS02 datastore. When a snapshot is created, the VM “test”, the snapshot redolog (-delta.vmdk) files are place in the working directory (home directory). So the snapshots files are created on datastore VMFS01.

[![snapshot-working esxi4](http://localhost/wp-content/uploads/2012/04/snapshot-working-esxi4_thumb1.jpg "snapshot-working esxi4")](http://localhost/wp-content/uploads/2012/04/snapshot-working-esxi41.jpg)

In ESXi 5 the snapshot delta disks are stored in the same home folder as the base disk. On every disk a snapshot file is created.

[![snapshot-working esxi5](http://localhost/wp-content/uploads/2012/04/snapshot-working-esxi5_thumb1.jpg "snapshot-working esxi5")](http://localhost/wp-content/uploads/2012/04/snapshot-working-esxi51.jpg)

I have seen VMware ESX(i) 3.x and 4.x environments were only the working directory (home directory) **is sized** to store snapshot files . The other datastores didn’t have enough room for storing snapshot files. So be sure before upgrading to vSphere 5 that all the datastores have enough free space to store snapshot files!

The snapshot location **can** changed in ESXi 5 but when performing a Storage vMotion, all the snapshot deltas will get migrated to the same folder as the VM’s base disk on the destination.

**Be sure to check this before upgrading to VMware vSphere 5!**

**More Information**:

- [Creating snapshots in a different location than default virtual machine directory](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1002929)
- [Changing the location of snapshot delta files for virtual machines in ESXi 5.0](http://kb.vmware.com/selfservice/microsites/search.do?cmd=displayKC&docType=kc&docTypeID=DT_KB_1_1&externalId=2007563)
- [Storage vMotion, Storage DRS &amp; Virtual Machine Snapshots Interoperability](http://blogs.vmware.com/vsphere/2011/09/storage-vmotion-storage-drs-virtual-machine-snapshots.html)
