---
author: Ivo Beerens
categories:
- Uncategorized
date: "2012-11-21T13:57:27Z"
guid: http://www.ivobeerens.nl/?p=1935
id: 1935
ssb_fbshare_counts:
- "11"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:11;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "11"
title: Useful ESXCLI commands for configuring and troubleshooting ESXi environments
url: /2012/11/21/useful-esxcli-commands-for-configuring-and-troubleshooting-esxi-environments/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

ESXCLI commands are very useful for configuring and troubleshooting ESXi servers. The vSphere vCLI 5.1 includes the following namespaces:

[![image](http://localhost/wp-content/uploads/2012/11/image_thumb.png "image")](http://localhost/wp-content/uploads/2012/11/image.png)

Here is a small list of some examples of ESXCLI commands:

### esxcli system

**Show ESXi version and build**

```
<pre lang="plain">esxcli system version get
```

**Enter Maintenance Mode**

```
<pre lang="plain">esxcli system maintenanceMode set –-enable yes
```

**Exit maintenance Mode**

```
<pre lang="plain">esxcli system maintenanceMode set --enable no
```

**List only advanced settings that have been changed from the system defaults**

```
<pre lang="plain">esxcli system settings advanced list –d
```

**List only kernel settings that have been changed from the system defaults**

```
<pre lang="plain">esxcli system settings kernel list –d
```

**List / Change / Test SNMP**

```
<pre lang="plain">esxcli system snmp get | hash | set | test
```

### esxcli vm

**List VMs on the ESXi server with the World ID**

```
<pre lang="plain">esxcli vm process list
```

**Kill a VM**

```
<pre lang="plain">esxcli vm process kill –t soft -w WorldID
```

### esxcli software

**Install updates and drivers on a ESXi host (make sure the ESXI host is MaintenanceMode)**

```
<pre lang="plain">esxcli software vib install -d /vmfs/volumes/VMFS01/patches/nameoftheupdate.zip
```

### esxcli network

**List physical NICs and connection state**

```
<pre lang="plain">esxcli network nic list
```

**List network information for the VM**

```
<pre lang="plain">esxcli network vm list
```

### esxcli storage

**List the devices currently controlled by the VMware NMP Multipath Plugin and show the SATP and PSP information associated with that device**

```
<pre lang="plain">esxcli storage nmp device list
```

**List VAAI properties for devices currently registered with the PSA.**

```
<pre lang="plain">esxcli storage core device vaai status get
```

**Change the default pathing policy to Round Robin**

```
<pre lang="plain">esxcli storage nmp satp set --default-psp VMW_PSP_RR --satp youre_satp_policy
```

More ESXCLI command can be found in the VMware ESXi 5.1 reference poster found [here](http://blogs.vmware.com/vsphere/files/2012/11/ESXi-5.1-Poster.pdf).
