---
author: Ivo Beerens
categories:
- Uncategorized
date: "2018-05-01T07:52:20Z"
guid: https://www.ivobeerens.nl/?p=5575
id: 5575
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- esxi
- VMware
title: Configure VM autostart in the ESXi Embedded Host Client
url: /2018/05/01/configure-vm-autostart-in-the-esxi-embedded-host-client/
---

For a standalone ESXi host I manage the host with the ESXi Embedded Host Client (HTML client). So no vCenter Server is used to manage this host. The standalone ESXi host is 24×7 up and running and has some critical infrastructure VMs for my lab and home environment. The critical VMs are automatically powered-on when when the ESXi host is booted with the autostart option in the host client.

In the latest versions of the Host Client (In vSphere 6.7 version 1.25 is included that already contains the autostart improvements) the autostart configuration is greatly improved what result in an easier configuration of autostart. if you are on vSphere 6.0 or 6.5 I suggest to upgrade to the latest ESXi Embedded Host Client before configuring autostart.

The upgrade of the Host client is easy, no maintenance mode and reboot of the ESXi host is needed. The upgrade can be done by following these steps:

- Download the latest VIB for here, [link](https://labs.vmware.com/flings/esxi-embedded-host-client)
- Upload the VIB on a datastore on your ESXi host
- SSH to the ESXi host
- Enter the following command to update the host client

\[code language=”text”\]esxcli software vib update -v /vmfs/volumes/<datastore>/<vibname.vib>```

[![](http://localhost/wp-content/uploads/2018/04/update-host-client-300x64.png)](http://localhost/wp-content/uploads/2018/04/update-host-client.png)

- Refesh the host client webpage (**https://<esxihostname>/ui/**)
- Check the version information in the host client (**Help -> About)**

[![](http://localhost/wp-content/uploads/2018/04/versionnew-300x144.png)](http://localhost/wp-content/uploads/2018/04/versionnew.png)

Configure autostart in the ESXi Embedded Host Client

- Open the ESXi host client by using the following URL: https://<esxihostname>/ui/
- Go to: **Manage** -> **System** -> **Autostart->Edit Settings**
    - Enable: Yes
    - Start delay: 60 seconds
    - Stop delay: 60 seconds
    - Stop action: shut down
    - Wait for heartbeat: yes
    - **Save**

[![](http://localhost/wp-content/uploads/2018/04/enable-300x139.png)](http://localhost/wp-content/uploads/2018/04/enable.png)

- Below the screen are the VMs listed. First enable autostart per VM by using the “Enable autostart for this VM” button.
- Once the autostart is enabled per VM, the order can be configured by increase or decrease the start order. The autostart order is displayed in the “autostart order” field.
- Configure the autostart and order for the VMs you want to automatically start when the ESXi server is booted.
- Reboot the ESXi host to test the autostart

With older versions of the ESXi Embedded Host Client it is “more complicated” to set the start order per VM. To set the autostart order with older versions:

- Enable autostart as described above

[![](http://localhost/wp-content/uploads/2018/04/1-300x163.png)](http://localhost/wp-content/uploads/2018/04/1.png)

- In the Virtual Machines section, right click on the field row and “Select columns”. Select the following columns: 
    - Autostart order
    - Start delay
    - Stop delay

[![](http://localhost/wp-content/uploads/2018/04/2-300x144.png)](http://localhost/wp-content/uploads/2018/04/2.png)

- Right click on the VM with the “Autostart order” status on Unset and select “increase” to enable autostart and set the order

[![](http://localhost/wp-content/uploads/2018/04/3-300x96.png)](http://localhost/wp-content/uploads/2018/04/3.png)

- Configure the autostart and order for the VMs you want to automatically start when the ESXi server is booted.
- Reboot the ESXi host to test the autostart
