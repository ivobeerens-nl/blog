---
title: "Configure the VMware Horizon View Event database with MS SQL Server Express"
date: "2013-02-07T14:40:57.000Z"
categories: 
  - "view"
  - "VMware"
tags: 
  - "view"
  - "VMware"
author: Ivo Beerens
---

In Proof of Concept (PoC) environments MS SQL Server Express can be used for the Event database. This procedure describes how-to create a event database by using an MS SQL Server Express database:

- Install the Microsoft SQL Server Management Studio. For more information see my earlier blog post  [link](https://www.ivobeerens.nl/2011/12/08/add-sql-server-management-studio-to-microsoft-sql-server-express-2008-r2/)
- Make sure the SQL server authentication is set to SQL and Windows Authentication mode
- Create a new database in Microsoft SQL Server Management Studio (There is no ODBC data source connection needed!).
- Create a new user using SQL Server authentication, disable enforce password policy and select as default database the event database.
- In the User Mapping field, map de the database and add the role **db\_owner** to the new user

<table border="0" width="400" cellspacing="0" cellpadding="2"><tbody><tr><td valign="top" width="200"><a href="images/image.png"><img style="background-image: none; padding-left: 0px; padding-right: 0px; display: inline; padding-top: 0px; border-width: 0px;" title="image" src="images/image_thumb.png" alt="image" width="244" height="217" border="0"></a></td><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2013/02/image1.png"><img style="background-image: none; padding-left: 0px; padding-right: 0px; display: inline; padding-top: 0px; border-width: 0px;" title="image" src="images/image_thumb1.png" alt="image" width="244" height="218" border="0"></a></td></tr></tbody></table>

- Open the SQL Server Configuration Manager > SQL Server Network Configuration > Protocols for VIM\_SQLEXP,  open the TCP/IP protocol and make sure it is enabled. Scroll down to IPAll and write down the TCP Dynamic Ports number

[![image](images/image_thumb2.png "image")](images/image2.png)

- Disable Windows Firewall on the SQL server machine. If you are unable to do this, set a Firewall exception for the dynamic port listed
- In the View Administrator (https://connectionserver/admin) select View Configuration > Event Configuration. In the Event Database section click Edit and enter the information needed.

<table border="0" width="400" cellspacing="0" cellpadding="2"><tbody><tr><td valign="top" width="200"><a href="images/image3.png"><img style="background-image: none; padding-left: 0px; padding-right: 0px; display: inline; padding-top: 0px; border-width: 0px;" title="image" src="images/image_thumb3.png" alt="image" width="226" height="244" border="0"></a></td><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2013/02/image4.png"><img style="background-image: none; padding-left: 0px; padding-right: 0px; display: inline; padding-top: 0px; border-width: 0px;" title="image" src="images/image_thumb4.png" alt="image" width="244" height="202" border="0"></a></td></tr></tbody></table>

And the Event database is configured with MS SQL Server Express.



