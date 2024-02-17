---
title: "Tips for upgrading to VMware vCenter 5.1"
date: "2012-09-13T12:53:12.000Z"
categories: 
  - "vcenter-2"
  - "vsphere51"
tags: 
  - "vcenter"
  - "vsphere51"
---

Before starting the upgrading to version 5.1 of the vCenter Server, the following steps can be taken to be able to successfully upgrade.  The first step is reading the upgrade guides:

- vSphere 5.1 upgrading guide, found [here](http://pubs.vmware.com/vsphere-51/index.jsp?topic=%2Fcom.vmware.vsphere.upgrade.doc%2FGUID-18B7B4BB-C24A-49CD-AE76-13285157B29F.html)
- Upgrading to vCenter 5.1 best practices, found [here](http://kb.vmware.com/selfservice/documentLinkInt.do?micrositeID=&popup=true&languageId=&externalID=2021193)
- Overview of upgrading from vCenter Server 5.0 to vCenter Server 5.1, found [here](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2032283)

After the RTFM stuff check the following:

- Make sure the SQL Server authentication checkbox is set to **SQL Server and Windows Authentication mode** on the SQL server. More info found [here](https://www.ivobeerens.nl/2012/09/11/vcenter-5-1-single-sign-on-error-during-installation/).
- The SQL server service is listening to port 1433. You can check this by using the following command:

> **_netstat –a | find “1433”_**

if the SQL Server is not listening on port 1433, use the following steps:

1. Open SQL Server Configuration Manage
2. Expand the SQL Server Network configuration
3. Click on the “Protocols for **SQLEXP\_VIM**”. **SQLEXP\_VIM** is the name of the SQL instance
4. Select TCP/IP – Properties – IP Addresses tab an scroll down to **IPALL,** enter value **1433** in the TCP Port field
5. Restart the SQL Server service

[![image](images/image_thumb8.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/09/image9.png)

- Open the sql script called “rsaIMSLiteMSSQLSetupTablespaces.sql”  (found in the vCenter ISO in …..\\Single Sign On\\DBScripts\\SSOServer\\schema\\mssql\\) and customize the location of the \*.mdf, \*.ndf and \*.lfd file to your needs. After customizing the SQL file execute it and make sure the RSA database is created.

[![image](images/image_thumb9.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/09/image10.png)

- If installing Single Sign On in a IPv6 environment check [this](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2035454) KB article
- If after upgrading the vCenter services hangs on startup check [this](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2035623) KB article
- The warning “**The Fully Qualified Domain Name cannot be resolved. If you continue the installation, some features might not work correctly**” appear during the installation. Make sure the reverse DNS record exist in the Reverse lookup Zones.  Test this with the nslookup command

[![image](images/image_thumb14.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/09/image15.png)

- The vCenter Server services hang on starup after upgrading to vCenter Server 5.1. More info can be found [here](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2035623).
