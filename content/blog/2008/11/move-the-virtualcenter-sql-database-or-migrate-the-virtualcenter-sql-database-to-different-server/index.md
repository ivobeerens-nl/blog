---
title: "Move the VirtualCenter SQL database or migrate the VirtualCenter SQL database to different server."
date: "2008-11-29T20:39:42.000Z"
categories: 
  - "database"
  - "virtualcenter"
  - "vmware"
tags: 
  - "database"
  - "virtualcenter"
  - "vmware"
---

VMware released two new handy KB articles about how to move or migrating  the SQL VirtualCenter database to different server.

To move the database

> When relocating your SQL database:
> 
> 1. To move SQL Server databases to a new location by using Detach and Attach functions in SQL Server, see Microsoft KB article [](http://support.microsoft.com/kb/224071/en-us)[http://support.microsoft.com/kb/224071/en-us](http://support.microsoft.com/kb/224071/en-us)
>     
> 2. If you are using the Copy Database Wizard in SQL Server 2000 see, Microsoft KB article [http://support.microsoft.com/kb/274463](http://support.microsoft.com/kb/274463)
>     
> 3. Update the Datasource (DSN) in the OBDC Administrator to reflect any changes made.
>     
> 4. If either the database login or password changed during the relocation, VirtualCenter must be updated to with the new credentials. For more information, see the _Modifying the username and password VirtualCenter uses to connect to the database server_ section of [Troubleshooting the database data source used by VirtualCenter Server (1003928)](http://kb.vmware.com/kb/1003928).
>     

[Read the KB article here.](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=7960893)

Migrate the database to a new server:

> 1. Shutdown the VirtualCenter Server service. For more information, see [Stopping, starting, or restarting the VirtualCenter Server service (1003895)](http://kb.vmware.com/kb/1003895).
>     
> 2. Take a backup of the SQL database.
>     
> 3. If the SQL database is also being moved, create a second instance of your database and use the vendor's tools to migrate the data.**Note**: For SQL Server, use Microsoft's Copy Database Wizard. For more information, see [http://support.microsoft.com/?kbid=274463](http://support.microsoft.com/?kbid=274463)
>     
>     . 
>     
>      
> 4. Create the appropriate System DSN connections on the new VirtualCenter Server host.
>     
> 5. Begin the installation of the VirtualCenter software on the new server. If you are installing VirtualCenter in a virtual machine, guidelines for deploying VirtualCenter in a virtual machine, including sizing, installation, functionality, and configuration of VMware HA can be found at [http://www.vmware.com/vmtn/resources/798](http://www.vmware.com/vmtn/resources/798).
>     
> 6. When prompted, select **Use existing database**, and provide the correct credentials to that database.
>     
> 7. When prompted, select to **not re-initialize the data**, as this erases all your inventory data.
>     
> 8. Reboot the virtual machine when the installation is finished.
>     
> 9. When you first start the VirtualCenter Client, it may ask for licenses. Configure the licenses as you had previously in your environment. For more information about licensing for ESX Server 3 hosts, see the Installation Guide. For more information about licensing for ESX Server 3i hosts, see the Setup Guide. You are now able to see the same settings and configuration details.**Note**: If the IP address of the new VirtualCenter Server has changed your ESX Servers must be made aware of that change, otherwise the ESX Servers continue to send their heartbeats to the original IP address of VirtualCenter and appear as Not Responding.To correct this situation: 
>     
>     1. Log in as root with an SSH client to each ESX host.
>         
>     2. Use a text editor to change the IP address inside the <serverIp>xxx.xxx.xxx.xxx</serverIp> tags the following file:/etc/opt/vmware/vpxa/vpxa.cfg (VirtualCenter 2.5.x) /etc/vmware/vpxa.cfg (VirtualCenter 2.0.x). 
>         
>     3. Save your changes and exit.
>         
>     4. Restart the management agents. For more information, see [Restarting the Management agents on an ESX Server (1003490)](http://kb.vmware.com/kb/1003490).
>         
>     5. Repeat for all ESX hosts connected to the VirtualCenter Server.
>         

 

[Read the KB article here.](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=5850444)

\[ad#verticaal\]
