---
title: "Unable to delete a VMDK because it&rsquo;s locked"
date: "2011-03-30T10:16:11.000Z"
categories: 
  - "vmware"
  - "vsphere"
tags: 
  - "vmware"
  - "vpshere"
---

When trying to delete an “old” VMDK file,  I've got  the following message “device **or resource is busy**”. I was pretty sure that the VMDK was not connected to any VM(s) anymore. I tried to delete the VMDK by command line and by using the datastore browser.

I found the VMware KB article  “[Virtual machine does not power on because of locked files”](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=10051)

This KB article describes how to find the VMware ESX host that holds the lock.

To identify the VMware ESX server that holds the lock, used the following command:

> vmkfstools -D /vmfs/volumes/<LUN/<name server.VMDK>

This command reports in the vmkernel.log the MAC address of the ESX server that holds the lock. Look in the vmkernel.log by using the following command:

> tail /var/log/vmkernel log

The vmkernel.log output:

> Mar 29 15:43:07 server vmkernel: 7:03:34:25.713 cpu9:4223)FS3: 142: <START                                                                                                                                                              server-flat.vmdk>  
> Mar 29 15:43:07 server vmkernel: 7:03:34:25.713 cpu9:4223)Lock \[type 10c00                                                                                                                                                             001 offset 31932416 v 142, hb offset 3272704  
> Mar 29 15:43:07 server vmkernel: gen 99305, mode 1, owner 4d39b32d-ef56720                                                                                                                                                            9-7754-**0025b3e1a4c8** mtime 3227617\]

The bold text is the MAC address of the VMware ESX server that holds the lock. Now we need to find the VMware ESX server that matches the MAC address. The following PowerCLI script displays all MAC address of all VMware ESX servers and displays this in a gridview.

<table style="border-collapse: separate" border="0" cellspacing="0" cellpadding="5"><tbody><tr><td style="border-bottom-style: none; padding-bottom: 5px; border-left-style: none; padding-left: 5px; padding-right: 5px; border-top-style: none; border-right-style: none; padding-top: 5px" valign="top"><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #cecece; font-size: ; padding-top: 5px"><font color="#000000"><font face="Consolas"><font style="font-size: 10pt">001</font></font><br></font></div></td><td style="border-bottom-style: none; padding-bottom: 5px; border-left-style: none; padding-left: 5px; padding-right: 5px; border-top-style: none; border-right-style: none; padding-top: 5px" valign="top" nowrap="nowrap"><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><span style="color: "><font style="font-size: 10pt" color="#000000">Connect-viserver vCenterserver</font></span></font></div><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><font color="#000000"><span style="color: "><font style="font-size: 10pt">Get-vmhostnetworkadapter</font></span><font style="font-size: 10pt"><span style="color: ">&nbsp;</span><span style="color: ">|</span><span style="color: ">&nbsp;</span><span style="color: ">Select</span><span style="color: ">&nbsp;</span><span style="color: ">vmhost</span><span style="color: ">,</span><span style="color: ">mac</span><span style="color: ">&nbsp;</span><span style="color: ">|</span><span style="color: ">&nbsp;</span><span style="color: ">Out-GridView</span></font></font></font></div></td></tr></tbody></table>

With a gridview it is possible to filter easily. Add the last part of the MAC address (including the : ) and the corresponding VMware ESX server is displayed:

[![2011-03-29 16h20_42](images/2011-03-29-16h20_42_thumb.jpg "2011-03-29 16h20_42")](https://www.ivobeerens.nl/wp-content/uploads/2011/03/2011-03-29-16h20_42.jpg)

On the VMware server that holds the lock restart the Management agents by using the following command:

> service mgmt-vmware restart

The lock disappeared and I was able to remove the VMDK file.
