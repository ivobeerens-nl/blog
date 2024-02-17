---
title: "VMware vShield drivers renamed in Guest Introspection drivers"
date: "2015-09-22T19:27:09.000Z"
---

The vShield Endpoint drivers are renamed as Guest Introspection Drivers. In VMware Tools there are two drivers available:

- NSX File Introspection Driver (**vsepflt.sys**)
- NSX Network Introspection Driver (**vnetflt.sys**)

These drivers can be installed separately now and allows you to install the file driver without installing the network driver. To install the vShield Endpoint Thin Agent driver (vsepflt.sys), select the NSX File Introspection Driver in VMware tools under VMCI Driver.

[![vShield driver](images/vShield-driver-300x235.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/09/vShield-driver.png)

For existing installations check if the vShield Endpoint Thin Agent driver is installed by using the following steps:

- Open 'msinfo32'
- Select Software Environment (1)
- Select System Drivers (2)
- Search for the vsepflt driver (3) and check if the driver is running

[![vsepflt](images/vsepflt-300x132.png)](https://www.ivobeerens.nl/wp-content/uploads/2015/09/vsepflt.png)
