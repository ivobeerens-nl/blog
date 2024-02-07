---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- Database
- VirtualCenter
- VMware
date: "2008-11-29T22:39:42Z"
guid: http://www.ivobeerens.nl/?p=221
id: 221
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Database
- VirtualCenter
- VMware
title: Move the VirtualCenter SQL database or migrate the VirtualCenter SQL database
  to different server.
url: /2008/11/29/move-the-virtualcenter-sql-database-or-migrate-the-virtualcenter-sql-database-to-different-server/
---

VMware released two new handy KB articles about how to move or migrating the SQL VirtualCenter database to different server.

To move the database

> <span style="font-size: 10pt"><span style="font-family: Arial;">When relocating your SQL database:</span></span>
> 
> 1. <div><span style="font-size: 10pt"><span style="font-family: Arial;">To move SQL Server databases to a new location by using Detach and Attach functions in SQL Server, see Microsoft KB article</span> [](http://support.microsoft.com/kb/224071/en-us)[<span style="color: #003399; font-family: Arial;">http://support.microsoft.com/kb/224071/en-us</span>](http://support.microsoft.com/kb/224071/en-us)</span></div>
> 2. <div><span style="font-family: Arial;"><span style="font-size: x-small;">If you are using</span> <span style="font-size: 10pt">the Copy Database Wizard in SQL Server 2000 see, Microsoft KB article</span></span> [<span style="font-size: x-small; color: #003399;">http://support.microsoft.com/kb/274463</span>](http://support.microsoft.com/kb/274463)</div>
> 3. <div><span style="font-size: 10pt"><span style="font-family: Arial;">Update the Datasource (DSN) in the OBDC Administrator to reflect any changes made.</span></span></div>
> 4. <div><span style="font-size: 10pt"><span style="font-family: Arial;">If either the database login or password changed during the relocation, VirtualCenter must be updated to with the new credentials. For more information, see the *Modifying the username and password VirtualCenter uses to connect to the database server* section of [<span style="color: #003399;">Troubleshooting the database data source used by VirtualCenter Server (1003928)</span>](http://kb.vmware.com/kb/1003928).</span></span></div>

[Read the KB article here.](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=7960893)

Migrate the database to a new server:

> <div class="comment_text"> </div>1. <div class="comment_text"><span style="font-size: x-small; font-family: Arial;">Shutdown the VirtualCenter Server service. For more information, see</span> [<span style="font-size: x-small; color: #003399; font-family: Arial;">Stopping, starting, or restarting the VirtualCenter Server service (1003895)</span>](http://kb.vmware.com/kb/1003895)<span style="font-size: x-small; font-family: Arial;">.</span></div>
> 2. <div class="comment_text"><span style="font-size: x-small; font-family: Arial;">Take a backup of the SQL database.</span></div>
> 3. <div class="comment_text"><span style="font-size: x-small; font-family: Arial;">If the SQL database is also being moved, create a second instance of your database and use the vendor’s tools to migrate the data.**Note**: For SQL Server, use Microsoft’s Copy Database Wizard. For more information, see [<span style="font-size: x-small; color: #003399; font-family: Arial;">http://support.microsoft.com/?kbid=274463</span>](http://support.microsoft.com/?kbid=274463)<div><span style="font-size: x-small; font-family: Arial;">.</span></div></span></div><div><span style="font-size: x-small; font-family: Arial;"> </span></div><span style="font-size: x-small; font-family: Arial;"> </span>
> 4. <div><span style="font-size: x-small; font-family: Arial;">Create the appropriate System DSN connections on the new VirtualCenter Server host.</span></div>
> 5. <div><span style="font-size: x-small; font-family: Arial;">Begin the installation of the VirtualCenter software on the new server. If you are installing VirtualCenter in a virtual machine, guidelines for deploying VirtualCenter in a virtual machine, including sizing, installation, functionality, and configuration of VMware HA can be found at</span> [<span style="font-size: x-small; color: #003399; font-family: Arial;">http://www.vmware.com/vmtn/resources/798</span>](http://www.vmware.com/vmtn/resources/798).</div>
> 6. <div><span style="font-size: x-small; font-family: Arial;">When prompted, select **Use existing database**, and provide the correct credentials to that database.</span></div>
> 7. <div><span style="font-size: x-small; font-family: Arial;">When prompted, select to **not re-initialize the data**, as this erases all your inventory data.</span></div>
> 8. <div><span style="font-size: x-small; font-family: Arial;">Reboot the virtual machine when the installation is finished.</span></div>
> 9. <div><span style="font-size: x-small; font-family: Arial;">When you first start the VirtualCenter Client, it may ask for licenses. Configure the licenses as you had previously in your environment. For more information about licensing for ESX Server 3 hosts, see the Installation Guide. For more information about licensing for ESX Server 3i hosts, see the Setup Guide. You are now able to see the same settings and configuration details.**Note**: If the IP address of the new VirtualCenter Server has changed your ESX Servers must be made aware of that change, otherwise the ESX Servers continue to send their heartbeats to the original IP address of VirtualCenter and appear as Not Responding.To correct this situation: </span></div>
>     1. <div><span style="font-size: x-small; font-family: Arial;">Log in as root with an SSH client to each ESX host.</span></div>
>     2. <div><span style="font-size: x-small; font-family: Arial;">Use a text editor to change the IP address inside the <span style="font-family: Courier New;"><serverIp>xxx.xxx.xxx.xxx</serverIp></span> tags the following file:<span style="font-family: Courier New;">/etc/opt/vmware/vpxa/vpxa.cfg</span> (VirtualCenter 2.5.x)  
>         <span style="font-family: Courier New;">/etc/vmware/vpxa.cfg</span> (VirtualCenter 2.0.x). </span></div>
>     3. <div><span style="font-size: x-small; font-family: Arial;">Save your changes and exit.</span></div>
>     4. <div><span style="font-size: x-small; font-family: Arial;">Restart the management agents. For more information, see</span> [<span style="font-size: x-small; color: #003399; font-family: Arial;">Restarting the Management agents on an ESX Server (1003490)</span>](http://kb.vmware.com/kb/1003490)<span style="font-size: x-small; font-family: Arial;">.</span></div>
>     5. <div><span style="font-size: x-small; font-family: Arial;">Repeat for all ESX hosts connected to the VirtualCenter Server.</span></div>

[Read the KB article here.](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=5850444)

<span style="font-family: Courier New;">\[ad#verticaal\]</span>
