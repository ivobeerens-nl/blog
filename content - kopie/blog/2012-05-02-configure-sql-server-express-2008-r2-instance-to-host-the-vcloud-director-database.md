---
author: Ivo Beerens
categories:
- sql
- vcd
- vcloud
date: "2012-05-02T09:40:44Z"
guid: http://www.ivobeerens.nl/?p=1525
id: 1525
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- SQL
- vcd
- vcloud
title: Configure SQL Server Express 2008 R2 instance to host the vCloud Director database
url: /2012/05/02/configure-sql-server-express-2008-r2-instance-to-host-the-vcloud-director-database/
---

This blog will explain how to configure the vCenter Server SQL Express 2008 R2 instance to host the vCloud Director database. This can be handy when you have limited resources in your test environment. SQL Server Express 2008 R2 is not a supported database for vCloud Director. For production environments check always first the VMware interoperability Matrix to know what’s supported .

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb.png "image")](http://localhost/wp-content/uploads/2012/05/image.png)

#### Steps:

- Make sure SQL Server Management Studio is installed on the vCenter server. See “[Add SQL Server Management Studio to Microsoft SQL Server Express 2008 R2](http://localhost/2011/12/08/add-sql-server-management-studio-to-microsoft-sql-server-express-2008-r2/)”
- Open SQL Server Management Studio
- Change Server Authentication to Mixed Authentication (SQL Server and Windows Authentication mode)

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb1.png "image")](http://localhost/wp-content/uploads/2012/05/image1.png)

- – Select “New Query”

[![image](http://localhost/wp-content/uploads/2012/05/image_thumb2.png "image")](http://localhost/wp-content/uploads/2012/05/image2.png)

- The following script (from [vCloud Director installation and configuration guide](http://www.vmware.com/pdf/vcd_15_install.pdf)) creates a database named “vcloud” on the c-drive and a special SQL user "vcloud” . Customize this script for your environment.
- Paste this script in the “New Query” window”<font color="#0000ff"><font color="#0000ff"></font></font>```
    <font color="#000000"><font size="2">USE </font><font face="Courier New" size="2">[master]</font><font face="Courier New" size="2"> </font>
    </font>
    ```
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
    <font color="#000000"><font face="Courier New" size="2">CREATE </font><font face="Courier New"><font size="2">DATABASE \[vcloud\] ON PRIMARY</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">(</font><font face="Courier New"><font size="2">NAME = N’vcloud’, FILENAME = N’C:\\vcloud.mdf’, SIZE = 100MB, FILEGROWTH = 10% )</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">LOG </font><font face="Courier New" size="2">ON</font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">(</font><font face="Courier New"><font size="2">NAME = N’vcdb\_log’, FILENAME = N’C:\\vcloud.ldf’, SIZE = 1MB, FILEGROWTH = 10%)</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">COLLATE </font><font face="Courier New" size="2">Latin1\_General\_CS\_AS</font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
     <font face="Courier New" size="2"></font>
    
    <font color="#000000" face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">USE </font><font face="Courier New" size="2">\[vcloud\]</font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
     <font face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">ALTER </font><font face="Courier New"><font size="2">DATABASE \[vcloud\] SET SINGLE\_USER WITH ROLLBACK IMMEDIATE;</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">ALTER </font><font face="Courier New"><font size="2">DATABASE \[vcloud\] SET ALLOW\_SNAPSHOT\_ISOLATION ON;</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">ALTER </font><font face="Courier New"><font size="2">DATABASE \[vcloud\] SET READ\_COMMITTED\_SNAPSHOT ON WITH NO\_WAIT;</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000"><font face="Courier New" size="2">ALTER </font><font face="Courier New"><font size="2">DATABASE \[vcloud\] SET MULTI\_USER;</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
    <font color="#000000" face="Courier New" size="2"></font>
    
     <font face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">USE </font><font face="Courier New" size="2">\[vcloud\]</font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
     <font face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">CREATE </font><font face="Courier New"><font size="2">LOGIN \[vcloud\] WITH PASSWORD = ‘vcloudpass’, DEFAULT\_DATABASE =\[vcloud\],</font></font><font face="Courier New"><font size="2"> DEFAULT\_LANGUAGE =\[us\_english\],CHECK\_POLICY=</font></font><font face="Courier New"><font size="2">OFF </font></font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
     <font face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">CREATE </font><font face="Courier New"><font size="2">USER \[vcloud\] for LOGIN \[vcloud\]</font></font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
     <font face="Courier New" size="2"></font>
    
    <font color="#000000" face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">USE </font><font face="Courier New" size="2">\[vcloud\]</font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font>
    
     <font face="Courier New" size="2"></font><font face="Courier New" size="2"></font>
    
    <font color="#000000"><font face="Courier New" size="2">sp\_addrolemember </font><font face="Courier New" size="2">\[db\_owner\], \[vcloud\]</font><font face="Courier New" size="2"> </font></font>
    
    <font color="#000000" face="Courier New" size="2">GO</font><font color="#0000ff"><font color="#0000ff"></font><font size="2"></font></font>
    
    
    - Execute the script (1) and make sure it has executed successfully (2)
    
    [![image](http://localhost/wp-content/uploads/2012/05/image_thumb3.png "image")](http://localhost/wp-content/uploads/2012/05/image3.png)
    
    
    - Open Start – All Programs – Microsoft SQL Server 2008 R2 – Configuration Tools – SQL Server Configuration Manager
    - Expand the “SQL Server Network Configuration” (1)
    - Select TCP/IP (2) and open the properties
    
    [![image](http://localhost/wp-content/uploads/2012/05/image_thumb4.png "image")](http://localhost/wp-content/uploads/2012/05/image4.png)
    
    
    - In the IPALL section, select the TCP port and fill in “1433”
    
    [![image](http://localhost/wp-content/uploads/2012/05/image_thumb5.png "image")](http://localhost/wp-content/uploads/2012/05/image5.png)
    
    
    - Restart the SQL Server (VIM\_SQLEXP) service
    
    [![image](http://localhost/wp-content/uploads/2012/05/image_thumb6.png "image")](http://localhost/wp-content/uploads/2012/05/image6.png)
    
    
    - Open the command prompt on the SQL Server and check if port 1433 is listening by using this command:
    
    ```
    <pre lang="plain">netstat -an | find "1433"
    ```
    
    [![image](http://localhost/wp-content/uploads/2012/05/image_thumb7.png "image")](http://localhost/wp-content/uploads/2012/05/image7.png)
    
    
    - Configure vCloud Director and point to the SQL Express instance
    
    ```
    <a href="http://localhost/wp-content/uploads/2012/05/image8.png"><img alt="image" border="0" decoding="async" height="350" loading="lazy" src="http://localhost/wp-content/uploads/2012/05/image_thumb8.png" style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" width="483"></img></a>
    ```
