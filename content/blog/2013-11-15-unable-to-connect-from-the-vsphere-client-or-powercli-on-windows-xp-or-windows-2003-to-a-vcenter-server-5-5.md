---
author: Ivo Beerens
categories:
- vcenter
- vcsa
- vSphere
date: "2013-11-15T08:54:34Z"
guid: http://www.ivobeerens.nl/?p=2579
id: 2579
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- client
- vCenter
- vcsa
- vSphere
title: Unable to connect from the vSphere Client or PowerCLI on Windows XP or Windows
  2003 to a vCenter Server 5.5
url: /2013/11/15/unable-to-connect-from-the-vsphere-client-or-powercli-on-windows-xp-or-windows-2003-to-a-vcenter-server-5-5/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

In my lab environment I still have a Windows XP with the vSphere Client 5.5 installed. When I try to connect with the vSphere Client or vSphere PowerCLI it faisl to connect to the vCenter Server 5.5 or vCenter Server Appliance (VCSA) 5.5. The following errors appears (The OS has a Dutch language installed):

[![image](http://localhost/wp-content/uploads/2013/11/image_thumb1.png "image")](http://localhost/wp-content/uploads/2013/11/image1.png)

PowerCLI error:

[![image](http://localhost/wp-content/uploads/2013/11/image_thumb2.png "image")](http://localhost/wp-content/uploads/2013/11/image2.png)

In the release notes of vSphere 5.5 this is a known issue:

> vSphere 5.5 uses the Open SSL library, which, for security, is configured by default to accept only connections that use strong cipher suites. On Windows XP or Windows Server 2003, the vSphere Client and vSphere PowerCLI do not use strong cipher suites to connect with vCenter Server. The error <tt>No matching cipher suite</tt> is shown on the server side, and the handshake fails on the vSphere Client or vSphere PowerCLI side.

There are three workarounds for this:

- Using Windows hotfixes on the Windows XP / 2003 OS
- Adjusting the vCenter Server configuration
- Adjusting the vCenter Server Appliance (VCSA) configuration

In the following steps I will adjust the vCenter Server Appliance configuration:

- Open a SSH connection to the VCSA
- login the appliance (by default this is <font face="Courier New">root</font> and with the passsword <font face="Courier New">vmware</font>)
- Navigate to the <font face="Courier New">/etc/vmware-vpx</font> directory
- Edit the <font face="Courier New">vpxd.cfg</font> file with for example the VI editor (<font face="Courier New">i</font> = insert)
- Add the following <font face="Courier New"><cipherList>ALL</cipherList></font> between the <font face="Courier New"><ssl></font> section (see screenshot below):

> <font face="Courier New"><ssl>   
> …   
> …   
> </ssl></font>

[![image](http://localhost/wp-content/uploads/2013/11/image_thumb3.png "image")](http://localhost/wp-content/uploads/2013/11/image3.png)

- Save the changes and quit the VI editor (<font face="Courier New">wq!</font>)
- Restart the vCenter Server service by using the following command: “<font face="Courier New">service vmware-vpxd restart</font>”

After the modification I was able to use the vSphere Client and PowerCLI to connect to the vCenter Server Appliance.

[![image](http://localhost/wp-content/uploads/2013/11/image_thumb4.png "image")](http://localhost/wp-content/uploads/2013/11/image4.png)

For more information see KB article 2049143 found here, [link](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2049143)
