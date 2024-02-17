---
title: "Enable the Intel 82579V NIC in Windows Server 2012"
date: "2012-08-08T13:59:22.000Z"
categories: 
  - "82579v"
  - "windows-server-2012"
tags: 
  - "82579v"
  - "windows-server-2012"
author: Ivo Beerens
---

Here are the steps:

- To be able to modify the drivers you need to run the the following commands:

bcdedit -set loadoptions DISABLE\_INTEGRITY\_CHECKS 
bcdedit -set TESTSIGNING ON 

  

- Reboot

- Download the Intel drivers. In my case I used the Intel drivers Asus has available for the Asus P9X79 motherboard

- Save them to a map and extract them if needed

- Open the folder **PRO1000**

- Open the folder **Winx64**

- Open the folder **NDIS63**

- Open the **e1c63x64.inf** file, I used Notepad++  to edit the file

- In the \[**ControlFlags**\] section delete the 3 lines (1)

- Select and copy the five **%E1503 lines** (2)

- Paste the 5 lines in the **\[Intel.NTamd64.6.2\]** section below the %1502NC lines

[![image](images/image_thumb15.png "image")](images/image16.png)

- After the modifications the **e1c63x64.inf** file must look like this:

[![image](images/image_thumb16.png "image")](images/image17.png)

- Save the file

- Install the Intel drivers

[![image](images/image_thumb17.png "image")](images/image18.png)

- After the installation the Intel 82579V Gigabit NIC is recognized and enabled

[![image](images/image_thumb18.png "image")](images/image19.png)

- Enable the driver integrity checks and disable test signing again by using the following commands:

bcdedit -set loadoptions ENABLE\_INTEGRITY\_CHECKS
bcdedit -set TESTSIGNING OFF

- Reboot

Now you can use the Intel 82579V Gigabit NIC  in Windows Server 2012.



