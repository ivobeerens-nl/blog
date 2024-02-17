---
author: Ivo Beerens
categories:
- PowerCLI
- Powershell
date: "2010-02-10T16:36:55Z"
guid: http://www.ivobeerens.nl/?p=509
id: 509
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- configuration
- post config
- PowerCLI
- Powershell
title: VMware ESX Post installation configuration via PowerCLI
url: /2010/02/10/vmware-esx-post-installation-configuration-via-powercli/
---

<font color="#000000" size="2"></font>

<font color="#000000" size="2">I made a simple example script using the VMware PowerCLI that can be used to do the post installation configuration of a VMware ESX 4 server. This script does the following things:</font>


- <font color="#000000"><font size="2">– Connect to VMware ESX server</font> </font>
- <font color="#000000"><font size="2">– Set the SC memory to 800MB</font> </font>
- <font color="#000000"><font size="2">– Creates vSwitch2 and add vmnic2 and vmnic3</font> </font>
- <font color="#000000"><font size="2">– Add several PortGroups and VLANs to vSwitch2</font> </font>
- <font color="#000000"><font size="2">– Remove default PortGroup VM Network</font> </font>
- <font color="#000000"><font size="2">– Creates a VMkernel VMotion port with IP address, subnetmask and VLAN</font> </font>
- <font color="#000000"><font size="2">– Add vmnic0 and vmnic1 to vSwitch0, set for the VMotion port vmnic1 active and vmnic0 standby and for the Service Console port vmnic0 active and vmnic1 standby</font> </font>
- <font color="#000000"><font size="2">– Configure NTP servers and open the firewall</font> </font>
- <font color="#000000"><font size="2">– Sets advanced settings Disk.UseDeviceReset to 0 and Disk.UseLUNReset to 1</font> </font>
- <font color="#000000"><font size="2">– Sets he Qlogic HBA queue depth and the Disk.SchedNumReqOutstandig to 64</font> </font>
- <font color="#000000" size="2">– Enable VMhost Startup and stop</font>

 <span style="color: #000000"> </span>

<font size="2">Here’s the listing of the script:</font>

 <span style="color: #008000">\#</span><span style="color: #008000"> Title: VMware ESX4 Post config #</span><span style="color: #008000">   
\#</span><span style="color: #008000"> Filename: esx4postconfig.sp1 # </span><span style="color: #008000">   
\#</span><span style="color: #008000"> Created by: Ivo Beerens # </span><span style="color: #008000">   
\#</span><span style="color: #008000"> Date: February 2010 # </span><span style="color: #008000">   
\#</span><span style="color: #008000"> Version: 1.0 #</span><span style="color: #008000">   
\#</span><span style="color: #008000"> Website: www.ivobeerens.nl # </span><span style="color: #008000">   
\#</span><span style="color: #008000"> E-mail: ivo\[AT\]ivobeerens.nl # </span><span style="color: #008000">   
</span><span style="color: #000000">   
</span><span style="color: #008000">\#</span><span style="color: #008000"> Variables #</span><span style="color: #008000">   
\#</span><span style="color: #008000"> vCenter name and port #</span><span style="color: #008000">   
</span><span style="color: #800080">$vcserver</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #800000">"</span><span style="color: #800000">vc01</span><span style="color: #800000">"</span><span style="color: #000000">   
</span><span style="color: #800080">$portvc</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #800000">"</span><span style="color: #800000">443</span><span style="color: #800000">"</span><span style="color: #000000">   
</span><span style="color: #008000">\#</span><span style="color: #008000">Service Console memory #</span><span style="color: #008000">   
</span><span style="color: #800080">$SCMemory</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #000000">800</span><span style="color: #000000">   
</span><span style="color: #008000">\#</span><span style="color: #008000"> default PortGroup #</span><span style="color: #008000">   
</span><span style="color: #800080">$DefaultPG</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0; font-weight: bold">Get-VirtualPortgroup</span><span style="color: #000000"> </span><span style="font-style: italic; color: #5f9ea0">-Name</span><span style="color: #000000"> </span><span style="color: #800000">‘</span><span style="color: #800000">VM Network</span><span style="color: #800000">‘</span><span style="color: #000000">   
</span><span style="color: #008000">\#</span><span style="color: #008000"> VMotion IP, subnetmask and VLAN</span><span style="color: #008000">   
</span><span style="color: #800080">$VMotionIP</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #800000">“</span><span style="color: #800000">172.16.1.50“   
$VMotionSubnet = “255.255.0.0“   
$VMotionVLan =</span><span style="color: #800000">"</span><span style="color: #000000">3</span><span style="color: #800000">"</span><span style="color: #800000">   
\# HBA Queue depth #   
$HBAqueudepth = 64   
\# vSwitch names #   
$Switch1 =</span><span style="color: #800000">"</span><span style="color: #000000">vSwitch0</span><span style="color: #800000">"</span><span style="color: #800000">   
$Switch2 =</span><span style="color: #800000">"</span><span style="color: #000000">vSwitch2</span><span style="color: #800000">"</span><span style="color: #800000"> </span>

Connect-VIServer $vcserver -User root -Password idontknow -port $portvc

\# Set SC memory to 800MB #   
Get-VMHost | Get-View | %{(Get-View -Id $\_.ConfigManager.MemoryManager).ReconfigureServiceConsoleReservation($SCMemory\*1mb)}

\# Create vSwitch1 and add vmnic2 and vmnic3 #   
New-VirtualSwitch -Name $Switch2 -Nic vmnic2,vmnic3

\# Add PortGroups and VLANs to the vSwitch2 #   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name<span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">999</span><span style="color: #000000"> Management</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 999   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">100</span><span style="color: #000000"> Servers</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 100   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">99</span><span style="color: #000000"> Clients Ser-D</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 99   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">98</span><span style="color: #000000"> Clients Ser-B</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 98   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">33</span><span style="color: #000000"> Secure LAN</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 33   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">32</span><span style="color: #000000"> DMZ</span><span style="color: #000000">3</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 32   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">31</span><span style="color: #000000"> DMZ</span><span style="color: #000000">1</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 31   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">30</span><span style="color: #000000"> DMZ</span><span style="color: #000000">0</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 30   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">7</span><span style="color: #000000"> VOiP</span><span style="color: #800000">"</span><span style="color: #800000"> -VLANID 7   
get-vmhost | Get-VirtualSwitch -Name $Switch2 | New-VirtualPortGroup -Name</span><span style="color: #800000">"</span><span style="color: #000000">VLAN</span><span style="color: #000000">1</span><span style="color: #000000"> </span><span style="color: #0000ff">Default</span><span style="color: #800000">"</span><span style="color: #800000"> </span>

\# Remove default Port Group after default installation #   
Remove-VirtualPortGroup -VirtualPortGroup $DefaultPG -Confirm:$false

\# Creates a VMkernel port VMotion on vSwitch0 #   
New-VMHostNetworkAdapter -PortGroup “VMotion“ -VirtualSwitch $Switch1 -IP $VMotionIP -SubnetMask $VMotionSubnet -VMotionEnabled:$true

\# Set VLAN of the VMotion VMkernel #   
$VMotionPG = Get-VirtualPortgroup -Name ‘VMotion’   
Set-VirtualPortGroup -VirtualPortGroup $VMotionPG -VlanId $VMotionVLan

\# Add vmnic0 and vmnic1 to vSwitch0 #   
$vs = get-virtualswitch -name $Switch0   
Set-VirtualSwitch -VirtualSwitch $vs -Nic vmnic0,vmnic1

\# Set VMotion vmnic1 active vmnic0 standby #   
get-virtualportgroup -name VMotion | Get-NicTeamingPolicy | Set-NicTeamingPolicy -MakeNicActive vmnic1   
get-virtualportgroup -name VMotion | Get-NicTeamingPolicy | Set-NicTeamingPolicy -MakeNicStandby vmnic0

\# Set Service Console vmnic0 active, vmnic1 standby #   
get-virtualportgroup -name ‘Service Console’ | Get-NicTeamingPolicy | Set-NicTeamingPolicy -MakeNicActive vmnic0   
get-virtualportgroup -name ‘Service Console’ | Get-NicTeamingPolicy | Set-NicTeamingPolicy -MakeNicStandby vmnic1

\# Configures NTP, add NTP servers, starts NTP and open the firewall port #   
Add-VmHostNtpServer -NtpServer <span style="color: #800000">"</span><span style="color: #000000">0.vmware.pool.ntp.org</span><span style="color: #800000">"</span><span style="color: #800000">   
Add-VmHostNtpServer -NtpServer </span><span style="color: #800000">"</span><span style="color: #000000">1.vmware.pool.ntp.org</span><span style="color: #800000">"</span><span style="color: #800000">   
Add-VmHostNtpServer -NtpServer </span><span style="color: #800000">"</span><span style="color: #000000">2.vmware.pool.ntp.org</span><span style="color: #800000">"</span><span style="color: #800000">   
Get-vmhostfirewallexception </span><span style="color: #800000">"</span><span style="color: #000000">NTP Client</span><span style="color: #800000">"</span><span style="color: #800000"> | Set-VMHostFirewallException -enabled:$true </span>

\# Advanced settings instellen #   
Set-VMHostAdvancedConfiguration -Name<span style="color: #800000">"</span><span style="color: #000000">Disk.UseDeviceReset</span><span style="color: #800000">"</span><span style="color: #800000"> -Value 0   
Set-VMHostAdvancedConfiguration -Name</span><span style="color: #800000">"</span><span style="color: #000000">Disk.UseLunReset</span><span style="color: #800000">"</span><span style="color: #800000"> -Value 1 </span>

\# Set the queuedepth for the Qlogic HBA and SchedNumReqOutstanding setting #   
Get-VMhostModule <span style="color: #800000">"</span><span style="color: #000000">qla2xxx</span><span style="color: #800000">"</span><span style="color: #800000"> | Set-VMHostModule -Options</span><span style="color: #800000">"</span><span style="color: #000000">ql2xmaxqdepth</span><span style="color: #ff0000">=</span><span style="color: #800080">$HBAqueudepth</span><span style="color: #800000">"</span><span style="color: #800000">   
Set-VMHostAdvancedConfiguration -Name</span><span style="color: #800000">"</span><span style="color: #000000">Disk.SchedNumReqOutstanding</span><span style="color: #800000">"</span><span style="color: #800000"> -Value $HBAqueudepth </span>

\# Enable VMHostStartup #   
$VMstart = Get-VMHostStartPolicy   
Set-VMHostStartPolicy -VMHostStartPolicy $VMstart -Enabled:$true -StartDelay 60 -StopDelay 60 -StopAction GuestShutDown

\# Disconnect #   
disconnect-viserver -confirm:$false

<font color="#000000" size="2">It’s easy to adjust the settings for your need. This shows the strength to use the PowerCLI for doing automation in VMware. If you have suggestions please let me know.</font>

\[ad#verticaal\]
