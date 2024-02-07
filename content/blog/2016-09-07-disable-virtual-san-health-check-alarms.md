---
author: Ivo Beerens
categories:
- VMware
- VSAN
date: "2016-09-07T08:38:44Z"
guid: http://www.ivobeerens.nl/?p=4755
id: 4755
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- Virtual SAN
- VSAN
title: Disable Virtual SAN health check alarms
url: /2016/09/07/disable-virtual-san-health-check-alarms/
---

When using PCIE/NVMe SSDs in the capacity layer of Virtual SAN, the SSDs are generating a warning for the “Hardware Compatibility – SCSI Controller on Virtual SAN HCL” health check, even when the devices are on the Virtual SAN HCL.

[![alarm](http://localhost/wp-content/uploads/2016/09/alarm-300x67.png)](http://localhost/wp-content/uploads/2016/09/alarm.png)

The “Hardware Compatibility – SCSI Controller on Virtual SAN HCL**”** health check cannot detect the PCIE/NVMe SSDs because they do not use standard I/O controllers.

To disable the HCL health check alarm use these simple steps:

- In the vCenter Web Client top level, navigate to Manage and select “**Alarm Definitions**“
- Navigate to the alarm and select **Edit**

[![alarm1](http://localhost/wp-content/uploads/2016/09/alarm1-300x140.png)](http://localhost/wp-content/uploads/2016/09/alarm1.png)

- Deselect the “**Enable this alarm**” checkbox and click on Finish

[![alarm3](http://localhost/wp-content/uploads/2016/09/alarm3-300x175.png)](http://localhost/wp-content/uploads/2016/09/alarm3.png)

Another use case is to disable the HCL health check(s) in non-production lab environments that use Virtual SAN with hardware that is not certified.
