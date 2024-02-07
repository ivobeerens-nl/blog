---
author: Ivo Beerens
categories:
- i217-V
- Whitebox
- windows server 2012
date: "2013-06-24T22:44:10Z"
guid: http://www.ivobeerens.nl/?p=2331
id: 2331
ssb_fbshare_counts:
- "13"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:13;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "13"
tags:
- I217-V
- Whitebox
- windows server 2012
title: Enable the Intel I217-V NIC in Windows Server 2012
url: /2013/06/24/enable-the-intel-i217-v-nic-in-windows-server-2012/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

My new Gigabyte Z87-D3HP motherboard with support for 4th Generation Intel® Core™ processors (codename Haswell) has a onboard Intel I217-V NIC. The NIC is not recognized and supported in Windows Server 2012. As with the “[Enable the Intel 82579V NIC in Windows Server 2012](http://localhost/2012/08/08/enable-the-intel-82579v-nic-in-windows-server-2012/)” blogpost it is possible to enable the NIC in Windows Server 2012. Here are the steps:

- To be able to modify the drivers you need to run the the following commands:

```
<pre lang="plain">bcdedit -set loadoptions DISABLE_INTEGRITY_CHECKS 
bcdedit -set TESTSIGNING ON
```

- **Reboot** the system
- Download the Intel drivers from the motherboard vendor or from Intel. In my case I used the Intel Windows 8 64-bit drivers Gigabyte has available for the Z87-D3HP motherboard on there website.

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb25.png "image")](http://localhost/wp-content/uploads/2013/06/image25.png)

- Save the drivers and extract them
- Open the folder **PRO1000**
- Open the folder **Winx64**
- Open the folder **NDIS63**
- Open the **e1d63x64.inf** file, I used Notepad++ to edit the file
- In the **\[ControlFlags\]** section delete the 3 lines (see 1)

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb26.png "image")](http://localhost/wp-content/uploads/2013/06/image26.png)

- Select and copy the three **E153B** lines ((see 2)
- Paste the 3 lines in the **\[Intel.NTamd64.6.2\]** section below the **%E155ANC** lines (see 3)
- After the modifications the **e1d63x64.inf** file must look like this:

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb27.png "image")](http://localhost/wp-content/uploads/2013/06/image27.png)

- Save the file
- Install the Intel driver
- During the installation the you got a “Windows can’t verify the publisher of this driver software” warning, select “Install this driver software anyway” and continue

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb28.png "image")](http://localhost/wp-content/uploads/2013/06/image28.png)

- After the installation the Intel I217-V Gigabit NIC is recognized and enabled.

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb29.png "image")](http://localhost/wp-content/uploads/2013/06/image29.png)

- Enable the driver integrity checks and disable test signing again by using the following commands:

```
<pre lang="plain">bcdedit -set loadoptions ENABLE_INTEGRITY_CHECKS
bcdedit -set TESTSIGNING OFF
```

- Reboot the system
