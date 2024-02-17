---
author: Ivo Beerens
categories:
- 82579v
- windows server 2012
date: "2012-08-08T15:59:22Z"
guid: http://www.ivobeerens.nl/?p=1724
id: 1724
ssb_fbshare_counts:
- "36"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:28;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "36"
tags:
- 82579v
- windows server 2012
title: Enable the Intel 82579V NIC in Windows Server 2012
url: /2012/08/08/enable-the-intel-82579v-nic-in-windows-server-2012/
---

After installing Windows Server 2012 on my homebrew server, the onboard Intel 82579V Gigabit NIC on the Asus P9X79 motherboard was not working. On the Asus site I found Windows 8 Intel drivers for the motherboard. After installing the drivers the NIC was still not working. To get the Intel 82579V NIC working in Windows Server 2012, I used the [this](http://homeservershow.com/forums/index.php?/topic/4025-intel-82579v-nic-on-ga-z77x-ud5h-and-other-motherboards-with-server-oss/) forum thread as reference for this blog post.

Here are the steps:

- To be able to modify the drivers you need to run the the following commands:

```
<pre lang="plain">bcdedit -set loadoptions DISABLE_INTEGRITY_CHECKS 
bcdedit -set TESTSIGNING ON 
```

- Reboot
- Download the Intel drivers. In my case I used the Intel drivers Asus has available for the Asus P9X79 motherboard
- Save them to a map and extract them if needed
- Open the folder **PRO1000**
- Open the folder **Winx64**
- Open the folder **NDIS63**
- Open the **e1c63x64.inf** file, I used Notepad++ to edit the file
- In the \[**ControlFlags**\] section delete the 3 lines (1)
- Select and copy the five **%E1503 lines** (2)
- Paste the 5 lines in the **\[Intel.NTamd64.6.2\]** section below the %1502NC lines

[![image](http://localhost/wp-content/uploads/2012/08/image_thumb15.png "image")](http://localhost/wp-content/uploads/2012/08/image16.png)

- After the modifications the **e1c63x64.inf** file must look like this:

[![image](http://localhost/wp-content/uploads/2012/08/image_thumb16.png "image")](http://localhost/wp-content/uploads/2012/08/image17.png)

- Save the file
- Install the Intel drivers

[![image](http://localhost/wp-content/uploads/2012/08/image_thumb17.png "image")](http://localhost/wp-content/uploads/2012/08/image18.png)

- After the installation the Intel 82579V Gigabit NIC is recognized and enabled

[![image](http://localhost/wp-content/uploads/2012/08/image_thumb18.png "image")](http://localhost/wp-content/uploads/2012/08/image19.png)

- Enable the driver integrity checks and disable test signing again by using the following commands:

```
<pre lang="plain">bcdedit -set loadoptions ENABLE_INTEGRITY_CHECKS
bcdedit -set TESTSIGNING OFF
```

- Reboot

Now you can use the Intel 82579V Gigabit NIC in Windows Server 2012.
