---
title: "Add SQL Server Management Studio to Microsoft SQL Server Express 2008 R2"
date: "2011-12-08T12:22:21.000Z"
categories: 
  - "sql-2"
  - "vcenter-2"
tags: 
  - "sql"
  - "vcenter"
---

When installing VMware vCenter 5 with the default database engine (Microsoft SQL Server Express 2008 R2) the SQL Management Studio is not installed by default. It can be confusing to add SQL Management studio at a later time. Here are the steps explained:

1\. Download Microsoft SQL Express 2008 R2 (can be found [here](http://www.microsoft.com/sqlserver/en/us/editions/express.aspx)) or browse the vCenter installation ZIP or ISO. The installation package can be found in the “\\redist\\SQLEXPR” folder.

2\. Select “**New Installation or add features to an existing installation**”.

[![2011-12-06 13h12_40](images/2011-12-06-13h12_40_thumb.jpg "2011-12-06 13h12_40")](https://www.ivobeerens.nl/wp-content/uploads/2011/12/2011-12-06-13h12_40.jpg)

3\. Select “**New installation or add shared features”.**

[![2011-12-06 13h14_41](images/2011-12-06-13h14_41_thumb.jpg "2011-12-06 13h14_41")](https://www.ivobeerens.nl/wp-content/uploads/2011/12/2011-12-06-13h14_41.jpg)

\- Only select “**Management Tools – Basic**”.

[![2011-12-06 13h15_07](images/2011-12-06-13h15_07_thumb.jpg "2011-12-06 13h15_07")](https://www.ivobeerens.nl/wp-content/uploads/2011/12/2011-12-06-13h15_07.jpg)

When the installation is completed you see the “SQL Server Management Studio” listed under the start menu.

[![2011-12-06 13h24_54](images/2011-12-06-13h24_54_thumb.jpg "2011-12-06 13h24_54")](https://www.ivobeerens.nl/wp-content/uploads/2011/12/2011-12-06-13h24_54.jpg)

Important to know is that you need exactly to follow these steps. If you choose the wrong option and  use the back button the “Management Tools – Basic” isn’t listed anymore. Strange….
