---
author: Ivo Beerens
categories:
- VMware
date: "2023-12-08T09:29:14Z"
guid: https://www.ivobeerens.nl/?p=9154
id: 9154
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- VMware
title: Patch a VMware ESXI host with the ESXCLI command and choose the right image
  profile
url: /2023/12/08/patch-a-vmware-esxi-hosts-with-esxcli-command-and-choose-the-right-image-profile/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

When installing a patch on a VMware ESXi host using the ESXCLI command you need to specify the image profile that is available in the ESXi patch.

Here are the steps for patching a VMware ESXi host with the correct image profile:

- Go to the[ Customer Connect Patch Downloads page.](https://my.vmware.com/group/vmware/patch#search)
- Download the patch needed, In this example, I use ESXi patch **VMware-ESXi-7.0U3o-22348816-depot.zip**
- Upload the patch to a datastore
- Make a SSH connection to the ESXi host
- Place the host in maintenance mode

```
esxcli system maintenanceMode set –enable-true
```

- Now you need to know which image profiles are available in the VMware ESXi patch. To do this use the following command (replace the **<datastore>** with your datastore):

```
esxcli software sources profile list -d /vmfs/volumes/<datastore>/iso/VMware-ESXi-7.0U3o-22348816-depot.zip
```

- The following profiles are listed. As you can see the image profile contains 4 image profiles:

![](http://localhost/wp-content/uploads/2023/12/1-1024x117.jpg)

- Here is a table with so, 0, standard, and no-tools means:

| **Option**  | **Details**                       |
|-------------|-----------------------------------|
| standard    | With VMware Tools included        |
| no-tools    | Without VMware Tools              |
| so          | Security updates only image       |
| o           | Security and Bugfix update image  |

- To install the ESXi with security and bugfix updates without VMware Tools use the following command (replace the **<datastore>** with your datastore):

```shell
esxcli software profile update -d /vmfs/volumes/<datastore>/VMware-ESXi-7.0U3o-22348816-depot.zip -p ESXi-7.0U3o-22348816-no-tools
```

- Reboot the host

```
esxcli system shutdown reboot -r "Patch ESXi 7.0U3"
```

- When the host is back, exit maintenance mode, make a SSH connection to the ESXi host

```
esxcli system maintenanceMode set --enable false
```

With this procedure, you can specify the right image profile when manually patching an ESXi host.
