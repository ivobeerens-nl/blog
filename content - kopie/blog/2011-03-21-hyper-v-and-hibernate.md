---
author: Ivo Beerens
categories:
- Hyper-V
date: "2011-03-21T11:41:44Z"
guid: http://www.ivobeerens.nl/?p=814
id: 814
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hyper-v
title: Hyper-V and hibernate
url: /2011/03/21/hyper-v-and-hibernate/
---

<font color="#000000">For my MS Hyper-V home server I want to hibernate every day between 12.30 and 07.00 am. When the Hyper-V role is installed, it is not possible to use the hibernate function. The following steps make it possible to automatic hibernate the system and when it wake up, the Hyper-V service and the VM(s) are started.</font>

<font color="#000000"></font>

<font color="#000000">Steps:</font>

<font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">**1.** Download “PowerShell Management Library for Hyper-V” file found </font>[<font color="#000000">here</font>](http://pshyperv.codeplex.com/)<font color="#000000">. Unblock the zone information from this zip, extract it and run the install file. Copy the content in the “HyperV\_install” folder to **“%windir%\\System32\\WindowsPowerShell\\v1.0\\Modules\\HyperV**”</font>

<font color="#000000"></font>

<font color="#000000">**2.** Edit VM properties of all VMs. Set the Automatic stop action “Shut down the guest operating system” </font>

[<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb6.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image6.png)

<font color="#000000"></font>

<font color="#000000">**3.** Edit the registy to disable auto start the **hvboot** service. When installing the hyper-v role the hibernate and sleep functionality is disabled. There is no way to use the hiberate or sleep functionality while the Hyper-v service is running. The Start property of a service can have the following values:</font>

<font color="#000000">0=Boot   
1=System (default)   
2=Auto   
**3=Demand**   
4=Disabled</font>

<font color="#000000">Set the value to 3, so that you can start the service when you want. 0 is not supported for hvboot. Information found </font>[<font color="#000000">here</font>](http://blogs.msdn.com/b/tejas/archive/2009/03/10/hibernate-and-sleep-with-hyper-v-role-enabled.aspx)<font color="#000000">. </font>

[<font color="#000000">![2011-03-19 10h48_49](http://localhost/wp-content/uploads/2011/03/2011-03-19-10h48_49_thumb.jpg "2011-03-19 10h48_49")</font>](http://localhost/wp-content/uploads/2011/03/2011-03-19-10h48_49.jpg)

<font color="#000000">Reboot the server so that the hvboot service is not started.</font>

<font color="#000000">**4.** Create 4 schedule tasks to run every day.</font>

<font color="#000000"></font>

| **<font color="#000000">Name</font>** | **<font color="#000000">Time</font>** | **<font color="#000000">Action</font>** |
|---|---|---|
| <font color="#000000">1.Reboot Server</font> | <font color="#000000">12.30 am</font> | <font color="#000000">shutdown /r t 30</font> |
| <font color="#000000">2.Hibernate</font> | <font color="#000000">12.40 am</font> | <font color="#000000">shutdown /h</font> |
| <font color="#000000">3.Wake Up</font> | <font color="#000000">07.00 am</font> | <font color="#000000">Under conditions select “Wake the computer to run this task”</font> |
| <font color="#000000">4.Start HVboot &amp; VMs</font> | <font color="#000000">07.10 am</font> | <font color="#000000">powershell.exe -command "c:\\powershell\\startvm.ps1"</font> |

 [<font color="#000000">![image](http://localhost/wp-content/uploads/2011/03/image_thumb7.png "image")</font>](http://localhost/wp-content/uploads/2011/03/image7.png)<font color="#000000"> </font>

<font color="#000000">The **startvm.ps1** script contains the following Powershell syntax:</font>

<div style="border-bottom: black 1px solid; border-left: black 1px solid; padding-bottom: 5px; padding-left: 5px; width: 444px; padding-right: 5px; font-family: ; height: 81px; font-size: ; overflow: auto; border-top: black 1px solid; border-right: black 1px solid; padding-top: 5px">| <div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #cecece; font-size: ; padding-top: 5px"><font face="Consolas"><font color="#000000" style="font-size: 10pt">001    002    003</font></font> </div> | <div style="padding-bottom: 5px; padding-left: 5px; padding-right: 5px; font-family: ; background: #fcfcfc; font-size: ; padding-top: 5px"><font face="Consolas"><span style="color: "><font color="#0000ff"><font style="font-size: 10pt">import-module</font></font></span><font style="font-size: 10pt"><span style="color: "><font color="#000000"> </font></span><span style="color: "><font color="#ff00ff">hyperv</font></span>    <span style="color: "><font color="#0000ff">start-service</font></span><span style="color: "><font color="#000000"> </font></span><span style="color: "><font color="#ff00ff">hvboot</font></span>    <span style="color: "><font color="#0000ff">start-vm</font></span><span style="color: "><font color="#000000"> </font></span><span style="color: "><font color="#00008b">-vm</font></span><span style="color: "><font color="#000000"> </font></span><span style="color: "><font color="#8b0000">"Windows Home Server 2011"</font></span><font color="#000000"> </font></font></font></div> |
|---|---|

</div><font color="#000000"></font>

<font color="#000000"></font>

<font color="#000000">Test if the schedule tasks are running fine by manually execute them and you’re ready to hibernate.</font>

<font color="#445864"> </font>
