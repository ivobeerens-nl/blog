---
title: "Hyper-V and hibernate"
date: "2011-03-21T09:41:44.000Z"
categories: 
  - "hyper-v"
tags: 
  - "hyper-v-2"
---

For my MS Hyper-V home server I want to hibernate every day between 12.30 and 07.00 am. When the Hyper-V role is installed, it is not possible to use the hibernate function. The following steps make it possible to automatic hibernate the system and when it wake up, the Hyper-V service and the VM(s) are started.

Steps:

**1.** Download “PowerShell Management Library for Hyper-V” file found [here](http://pshyperv.codeplex.com/). Unblock the zone information from this zip, extract it and run the install file. Copy the content in the “HyperV\_install” folder to **“%windir%\\System32\\WindowsPowerShell\\v1.0\\Modules\\HyperV**”

**2.** Edit VM properties of all VMs. Set the Automatic stop action “Shut down the guest operating system”

[![image](images/image_thumb6.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/03/image6.png)

**3.** Edit the registy to disable auto start the **hvboot** service. When installing the hyper-v role the hibernate and sleep functionality is disabled.  There is no way to use the hiberate or sleep functionality while the Hyper-v service is running.  The Start property of a service can have the following values:

0=Boot  
1=System (default)  
2=Auto  
**3=Demand**  
4=Disabled

Set the value to 3, so that you can start the service when you want. 0 is not supported for hvboot. Information found [here](http://blogs.msdn.com/b/tejas/archive/2009/03/10/hibernate-and-sleep-with-hyper-v-role-enabled.aspx).

[![2011-03-19 10h48_49](images/2011-03-19-10h48_49_thumb.jpg "2011-03-19 10h48_49")](https://www.ivobeerens.nl/wp-content/uploads/2011/03/2011-03-19-10h48_49.jpg)

Reboot the server so that the hvboot service is not started.

**4.** Create 4 schedule tasks to run every day.

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="133"><strong><font color="#000000">Name</font></strong></td><td valign="top" width="133"><strong><font color="#000000">Time</font></strong></td><td valign="top" width="133"><strong><font color="#000000">Action</font></strong></td></tr><tr><td valign="top" width="133"><font color="#000000">1.Reboot Server</font></td><td valign="top" width="133"><font color="#000000">12.30 am</font></td><td valign="top" width="133"><font color="#000000">shutdown /r t 30</font></td></tr><tr><td valign="top" width="133"><font color="#000000">2.Hibernate</font></td><td valign="top" width="133"><font color="#000000">12.40 am</font></td><td valign="top" width="133"><font color="#000000">shutdown /h</font></td></tr><tr><td valign="top" width="133"><font color="#000000">3.Wake Up</font></td><td valign="top" width="133"><font color="#000000">07.00 am</font></td><td valign="top" width="133"><font color="#000000">Under conditions select “Wake the computer to run this task”</font></td></tr><tr><td valign="top" width="133"><font color="#000000">4.Start HVboot &amp; VMs</font></td><td valign="top" width="133"><font color="#000000">07.10 am</font></td><td valign="top" width="133"><font color="#000000">powershell.exe -command "c:\powershell\startvm.ps1"</font></td></tr></tbody></table>

[![image](images/image_thumb7.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/03/image7.png) 

The **startvm.ps1** script contains the following Powershell syntax:

<table style="border-collapse: separate" border="0" cellspacing="0" cellpadding="5"><tbody><tr><td style="border-bottom-style: none; padding-bottom: 5px; border-left-style: none; padding-left: 5px; padding-right: 5px; border-top-style: none; border-right-style: none; padding-top: 5px" valign="top"><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #cecece; font-size: ; padding-top: 5px"><font face="Consolas"><font style="font-size: 10pt" color="#000000">001<br>002<br>003</font></font><br></div></td><td style="border-bottom-style: none; padding-bottom: 5px; border-left-style: none; padding-left: 5px; padding-right: 5px; border-top-style: none; border-right-style: none; padding-top: 5px" valign="top" nowrap="nowrap"><div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><span style="color: "><font color="#0000ff"><font style="font-size: 10pt">import-module</font></font></span><font style="font-size: 10pt"><span style="color: "><font color="#000000">&nbsp;</font></span><span style="color: "><font color="#ff00ff">hyperv</font></span><br><span style="color: "><font color="#0000ff">start-service</font></span><span style="color: "><font color="#000000">&nbsp;</font></span><span style="color: "><font color="#ff00ff">hvboot</font></span><br><span style="color: "><font color="#0000ff">start-vm</font></span><span style="color: "><font color="#000000">&nbsp;</font></span><span style="color: "><font color="#00008b">-vm</font></span><span style="color: "><font color="#000000">&nbsp;</font></span><span style="color: "><font color="#8b0000">"Windows Home Server 2011"</font></span><font color="#000000"></font></font></font></div></td></tr></tbody></table>

Test if the schedule tasks are running fine by manually execute them and you’re ready to hibernate.
