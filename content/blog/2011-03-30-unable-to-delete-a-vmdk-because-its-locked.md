---
author: Ivo Beerens
categories:
- VMware
- vSphere
date: "2011-03-30T12:16:11Z"
guid: http://www.ivobeerens.nl/?p=819
id: 819
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware
- vpshere
title: Unable to delete a VMDK because it&rsquo;s locked
url: /2011/03/30/unable-to-delete-a-vmdk-because-its-locked/
---

<font color="#000000">When trying to delete an “old” VMDK file, I’ve got the following message “device **or resource is busy**”. I was pretty sure that the VMDK was not connected to any VM(s) anymore. I tried to delete the VMDK by command line and by using the datastore browser.</font>

<font color="#000000">I found the VMware KB article “</font>[<font color="#000000">Virtual machine does not power on because of locked files”</font>](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=10051)

<font color="#000000">This KB article describes how to find the VMware ESX host that holds the lock.</font>

<font color="#000000">To identify the VMware ESX server that holds the lock, used the following command:</font>

> <font color="#000000">vmkfstools -D /vmfs/volumes/<LUN/<name server.VMDK></font>

<font color="#000000">This command reports in the vmkernel.log the MAC address of the ESX server that holds the lock. Look in the vmkernel.log by using the following command:</font>

> <font color="#000000">tail /var/log/vmkernel log</font>

**<font color="#000000"></font>**

<font color="#000000">The vmkernel.log output:</font>

> <font color="#000000"><font size="1">Mar 29 15:43:07 server vmkernel: 7:03:34:25.713 cpu9:4223)FS3: 142: <START server-flat.vmdk>   
> Mar 29 15:43:07 server vmkernel: 7:03:34:25.713 cpu9:4223)Lock \[type 10c00 001 offset 31932416 v 142, hb offset 3272704   
> Mar 29 15:43:07 server vmkernel: gen 99305, mode 1, owner 4d39b32d-ef56720 9-7754-</font><font size="3">**0025b3e1a4c8**</font><font size="1"> mtime 3227617\] </font></font>

<font color="#000000">The bold text is the MAC address of the VMware ESX server that holds the lock. Now we need to find the VMware ESX server that matches the MAC address. The following PowerCLI script displays all MAC address of all VMware ESX servers and displays this in a gridview.</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<div style="border-bottom: black 1px solid; border-left: black 1px solid; padding-bottom: 5px; padding-left: 5px; width: 632px; padding-right: 5px; font-family: ; height: 68px; font-size: ; overflow: auto; border-top: black 1px solid; border-right: black 1px solid; padding-top: 5px">| <div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #cecece; font-size: ; padding-top: 5px"><font color="#000000"><font face="Consolas"><font style="font-size: 10pt">001</font></font>    </font></div> | <div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><span style="color: "><font color="#000000" style="font-size: 10pt">Connect-viserver vCenterserver</font></span></font></div><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><font color="#000000"><span style="color: "><font style="font-size: 10pt">Get-vmhostnetworkadapter</font></span><font style="font-size: 10pt"><span style="color: "> </span><span style="color: ">\|</span><span style="color: "> </span><span style="color: ">Select</span><span style="color: "> </span><span style="color: ">vmhost</span><span style="color: ">,</span><span style="color: ">mac</span><span style="color: "> </span><span style="color: ">\|</span><span style="color: "> </span><span style="color: ">Out-GridView</span> </font></font></font></div> |
|---|---|

</div><font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">With a gridview it is possible to filter easily. Add the last part of the MAC address (including the : ) and the corresponding VMware ESX server is displayed:</font>

<font color="#000000"></font>

<font color="#000000"></font>

<a></a>[<font color="#000000">![2011-03-29 16h20_42](http://localhost/wp-content/uploads/2011/03/2011-03-29-16h20_42_thumb.jpg "2011-03-29 16h20_42")</font>](http://localhost/wp-content/uploads/2011/03/2011-03-29-16h20_42.jpg)

<font color="#000000"></font>

<font color="#000000">On the VMware server that holds the lock restart the Management agents by using the following command:</font>

> <font color="#000000">service mgmt-vmware restart </font>

<font color="#000000">The lock disappeared and I was able to remove the VMDK file.</font>

<font color="#000000"></font>

<font color="#000000"> </font>

<font color="#000000"></font>

<font color="#000000"></font>
