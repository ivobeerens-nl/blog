---
author: Ivo Beerens
categories:
- vpshere 5
- windows 8
date: "2012-02-29T19:55:05Z"
guid: http://www.ivobeerens.nl/?p=1356
id: 1356
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- vpshere 5
- windows 8
title: Install Windows 8 Consumer Preview as VM in VMware vSphere 5
url: /2012/02/29/install-windows-8-consumer-preview-as-vm-in-vmware-vsphere-5/
---

<font color="#000000">Today the Windows 8 Consumer Preview is launched. To install the Windows 8 Consumer Preview as VM in VMware vSphere 5, use the following steps:</font>

<font color="#000000">1. Install VMware ESXi 5.0 patch release </font>[<font color="#000000">ESXi500-201112001</font>](http://kb.vmware.com/selfservice/microsites/search.do?cmd=displayKC&docType=kc&docTypeID=DT_KB_1_1&externalId=2007680)<font color="#000000">. If you didn’t install the patch the following screen appears when booting the Windows 8 ISO:</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb14.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image16.png)

> <font color="#000000">Your computer ran into a problem and needs to restart</font>

<font color="#000000"></font>

<font color="#000000">2. When the patch is installed, create a new VM and choose the following settings:</font>

<font color="#000000"></font>

| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb15.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image17.png) | [![image](http://localhost/wp-content/uploads/2012/03/image_thumb4.png "image")](http://localhost/wp-content/uploads/2012/03/image4.png) |
|---|---|
| <font color="#000000">1. Choose custom</font> | <font color="#000000">2. Enter VM Name</font> |
| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb17.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image19.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb18.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image20.png) |
| <font color="#000000">3. Select datastore</font> | <font color="#000000">4. Virtual Machine Version 8</font> |
| [![image](http://localhost/wp-content/uploads/2012/03/image_thumb5.png "image")](http://localhost/wp-content/uploads/2012/03/image5.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb20.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image22.png) |
| <font color="#000000">5. Choose Microsoft Windows 7 64-bit</font> | <font color="#000000">6. Select the amount of processor and cores needed</font> |
| [![image](http://localhost/wp-content/uploads/2012/03/image_thumb6.png "image")](http://localhost/wp-content/uploads/2012/03/image6.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb22.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image24.png) |
| <font color="#000000">7. Enter memory</font> | <font color="#000000">8. Select E1000 network adapter</font> |
| [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb23.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image25.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb24.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image26.png) |
| <font color="#000000">9. Select default SCSI controller</font> | <font color="#000000">10. Create New disk</font> |
| [![image](http://localhost/wp-content/uploads/2012/03/image_thumb7.png "image")](http://localhost/wp-content/uploads/2012/03/image7.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb26.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image28.png) |
| <font color="#000000">11. Enter the desired disk size (default)</font> | <font color="#000000">12 Select controller</font> |
| [![image](http://localhost/wp-content/uploads/2012/03/image_thumb8.png "image")](http://localhost/wp-content/uploads/2012/03/image8.png) | <font color="#000000"></font> |
| <font color="#000000">13. Finish</font> | <font color="#000000"></font> |

<font color="#000000"></font>

<font color="#000000">3. Edit the VM configuration and change the following settings:</font>

| [![image](http://localhost/wp-content/uploads/2012/03/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/03/image3.png) | [<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb29.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image31.png) |
|---|---|
| <font color="#000000">Enable 3D graphics</font> | <font color="#000000">Choose the Windows 8 ISO to boot from</font> |
| [![image](http://localhost/wp-content/uploads/2012/03/image_thumb9.png "image")](http://localhost/wp-content/uploads/2012/03/image9.png) |  |
| <font color="#000000">Select as guest OS “Microsoft Windows 8 Server (64-bit)”</font> | <font color="#000000"></font> |

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">4. Boot the VM and install Windows 8</font>

<font color="#000000"></font>

<font color="#000000">Now you’re able to install Windows 8 as VM in VMware vSphere 5. </font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2012/02/image_thumb31.png "image")</font>](http://localhost/wp-content/uploads/2012/02/image33.png)

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">More information can be found </font>[<font color="#000000">here</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2006859)<font color="#000000">.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#ff0000">Updated: March 8 2012, Removed typos in blog.</font>

\[ad#banner\]
