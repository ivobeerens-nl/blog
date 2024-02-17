---
author: Ivo Beerens
categories:
- ESX
- ESXi
- Tools
date: "2011-12-05T19:31:53Z"
guid: http://www.ivobeerens.nl/2011/12/05/tool-esx-system-analyzer/
id: 1166
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- ESX
- esxi
- Tools
title: Migrate to VMware ESXi? Use the &ldquo;ESX System Analyzer&rdquo; tool
url: /2011/12/05/tool-esx-system-analyzer/
---

<font color="#000000">VMware Flings did it again. They released another cool tool called “ESX System Analyzer”. This tool helps when you want to migrate from VMware ESX to VMware ESXi. It scans the VMware environment and collects the following information:</font>

<font color="#000000">– Hardware compatibility with ESXi. It checks if the hardware is compatible with ESXi 4 and ESXi 5. </font>

<font color="#000000">– VMs registered on the ESX host, as well as VMs located on the host’s local disk</font>

<font color="#000000">– Modifications to the Service Console   
 – RPMs which have been added or removed   
 – Files which have been added   
 – Users and cronjobs which have been added</font>

<font color="#000000">This tool also provides summary information for the whole existing environment</font>

<font color="#000000">– Version of VMware Tools and Virtual Hardware for all VMs</font>

<font color="#000000">– Version of Filesystem for all datastores</font>

<font color="#000000">By having this information, administrators can determine what tasks need to be done prior to the migration. Examples include:</font>

<font color="#000000">– Relocate VMs from local datastores to shared datastores</font>

<font color="#000000">– Make note of what agent software has been added to the host and obtain the equivalent agentless version</font>

<font color="#000000">– Replace cronjobs with equivalent remote scripts written with PowerCLI or vCLI</font>

<font color="#000000"></font>

<font color="#000000">The installation and configuration of the “ESX System Analyzer” appliance is very easy. </font><font color="#000000">Here are some screenshots of the appliance:</font>

<font color="#000000"></font>

| [<font color="#000000">![image](http://localhost/wp-content/uploads/2011/12/image_thumb.png "image")</font>](http://localhost/wp-content/uploads/2011/12/image.png) | [<font color="#000000">![2011-12-05 15h14_18](http://localhost/wp-content/uploads/2011/12/2011-12-05-15h14_18_thumb.jpg "2011-12-05 15h14_18")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-05-15h14_18.jpg) |
|---|---|
| [<font color="#000000">![2011-12-05 15h19_56](http://localhost/wp-content/uploads/2011/12/2011-12-05-15h19_56_thumb.jpg "2011-12-05 15h19_56")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-05-15h19_56.jpg) | <font color="#000000"></font> |

<font color="#000000"></font>

<font color="#000000">Screenshots of the Output in XLS (Excel):</font>

<font color="#000000"></font>

<font color="#000000">**Overview output:**</font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/12/image_thumb1.png "image")</font>](http://localhost/wp-content/uploads/2011/12/image1.png)

<font color="#000000"></font>

<font color="#000000">**ESX server output:**</font>

[<font color="#000000">![2011-12-05 15h24_11](http://localhost/wp-content/uploads/2011/12/2011-12-05-15h24_11_thumb.jpg "2011-12-05 15h24_11")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-05-15h24_11.jpg)

<font color="#000000"></font>

<font color="#000000">This is a very handy tool when you want to migrate from VMware ESX to ESXi. </font><font color="#000000">More information can be found on the VMware Flings website found </font>[<font color="#000000">here</font>](http://labs.vmware.com/flings/esx-system-analyzer)<font color="#000000">.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>
