---
author: Ivo Beerens
categories:
- VMware
- VSAN
date: "2014-03-06T19:55:12Z"
guid: http://www.ivobeerens.nl/?p=2688
id: 2688
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- VMware
- VSAN
title: VMware VSAN Launch Q&amp;A
url: /2014/03/06/vmware-vsan-launch-qa/
---

VMware has today announced VSAN. Here are some highlights from the Q&amp;A session:

- VSAN will be GA at March 10 2014
- vSphere 5.5 Update 1 will support VSAN GA
- Beta VSAN upgrades to the GA release are not supported
- VSAN is not a VSA. Performance is much better than any VSA
- Pricing and packaging will covered on the GA date
- Performance of VSAN scales linear as you add more hardware (extra nodes with storage)
- Initial release of VSAN requires SSD and HDD. So using only SSD disks and no HDDs it not possible
- VSAN use cases are for example: VDI, Tier 2/3 workloads and Disaster Recovery cases
- VMware Horizon View will be supported in the GA release
- The minimum for VSAN is 3 ESXi nodes and the maximum is 32 nodes
- The minimum is 1 HDD and 1 SSD. The maximum is 35 HDDs and one SSD per 7 HDDs
- Minimum NIC speed is 1 Gbps, recommended NIC speed is 10 Gbps
- Replication is synchronously
- Every seven HDDs needs a SSD. SSD and HDD Ratio is 1:10 (GB)
- No de-dupe is supported in the GA version
- Hardware vendors such as Dell, HP and Cisco will support VSAN as VSAN Ready nodes. Watch the VMware Compatibility Guide at GA. [Link](http://www.vmware.com/resources/compatibility/search.php?deviceCategory=vsan)
- You can build your own VSAN with certified hardware
- There will be 13 pre configurations solutions available on the GA date

[![image](http://localhost/wp-content/uploads/2014/03/image_thumb.png "image")](http://localhost/wp-content/uploads/2014/03/image.png)

- JBOD is not supported in the GA release
- What is the difference with MS storage spaces: MS Storage spaces is presenting a file server from dedicated servers and JBODs. VSAN is object storage and doesn’t require dedicated servers, it uses the same servers you have for your compute, and other benefits like flash cache acceleration, storage policy management and automation and more.
