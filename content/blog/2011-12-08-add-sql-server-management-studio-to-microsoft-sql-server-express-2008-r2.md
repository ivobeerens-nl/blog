---
author: Ivo Beerens
categories:
- sql
- vcenter
date: "2011-12-08T13:22:21Z"
guid: http://www.ivobeerens.nl/2011/12/08/add-sql-server-management-studio-to-microsoft-sql-server-express-2008-r2/
id: 1178
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- SQL
- vCenter
title: Add SQL Server Management Studio to Microsoft SQL Server Express 2008 R2
url: /2011/12/08/add-sql-server-management-studio-to-microsoft-sql-server-express-2008-r2/
---

<font color="#000000">When installing VMware vCenter 5 with the default database engine (Microsoft SQL Server Express 2008 R2) the SQL Management Studio is not installed by default. It can be confusing to add SQL Management studio at a later time. Here are the steps explained:</font>

<font color="#000000"></font>

<font color="#000000">1. Download Microsoft SQL Express 2008 R2 (can be found </font>[<font color="#000000">here</font>](http://www.microsoft.com/sqlserver/en/us/editions/express.aspx)<font color="#000000">) <strike>or browse the vCenter installation ZIP or</strike> <strike>ISO. The installation package can be found in the “\\redist\\SQLEXPR” folder.</strike></font>

<font color="#000000">2. Select “**New Installation or add features to an existing installation**”.</font>

[<font color="#000000">![2011-12-06 13h12_40](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h12_40_thumb.jpg "2011-12-06 13h12_40")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h12_40.jpg)

<font color="#000000">3. Select “**New installation or add shared features”.**</font>

[<font color="#000000">![2011-12-06 13h14_41](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h14_41_thumb.jpg "2011-12-06 13h14_41")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h14_41.jpg)

<font color="#000000">– Only select “**Management Tools – Basic**”. </font>

[<font color="#000000">![2011-12-06 13h15_07](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h15_07_thumb.jpg "2011-12-06 13h15_07")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h15_07.jpg)

<font color="#000000">When the installation is completed you see the “SQL Server Management Studio” listed under the start menu.</font>

[<font color="#000000">![2011-12-06 13h24_54](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h24_54_thumb.jpg "2011-12-06 13h24_54")</font>](http://localhost/wp-content/uploads/2011/12/2011-12-06-13h24_54.jpg)

<font color="#000000"></font>

<font color="#000000">Important to know is that you need exactly to follow these steps. If you choose the wrong option and use the back button the “Management Tools – Basic” isn’t listed anymore. Strange….</font>
