---
author: Ivo Beerens
categories:
- Hyper-V
- Powershell
- scvmm
date: "2013-01-28T11:07:16Z"
guid: http://www.ivobeerens.nl/?p=2155
id: 2155
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
tags:
- hyper-v
- Powershell
- scvmm
title: Health Check your System Center Virtual Machine Server (SCVMM) 2012 environent
  with PowerShell
url: /2013/01/28/health-check-your-system-center-virtual-machine-server-scvmm-2012-environent-with-powershell/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

Last week I created a simple example of a Healt Check PowerShell script that connects to Microsoft System Center Virtual Machine Manager and displays information about the Hyper-V hosts and VMs managed by this server.

I run the PowerShell script from another Windows Server 2012 host. To make this work make sure the Hyper-V manager and the VMM Console is installed on the server. The VMM console can be installed from the Microsoft System Center 2012 Virtual Machine Manager ISO.

The output is displayed on the screen and exported to a HTML file. The following information is generated:

**Host information:**

Cluster it belongs, host name, CPU count, core count, CPU speed, CPU model, memory, operating System, and VM hostgroup

**VM information:**

VM name, computer name, host the VM is on, CPU count, CPU type, memory, if dynamic Memory is enabled, Operating System, If integration tools are installed, integration tool version, VM status, Replication Status and VM location

**VM snapshot information:**

VM Name, Name of the snapshot, description, time added and modified time

Here is an example how the output looks like:

[![image](http://localhost/wp-content/uploads/2013/01/image_thumb8.png "image")](http://localhost/wp-content/uploads/2013/01/image8.png)

The only parameter that needs to be changed is the **$File** variable that specify the location were the HTML file is stored.

**PowerShell script:**

```
<span style="color: #008000"><#
.</span><span style="color: #008000">SYNOPSIS</span><span style="color: #008000">
  </span><span style="color: #008000">System</span><span style="color: #008000"> </span><span style="color: #008000">Center</span><span style="color: #008000"> </span><span style="color: #008000">Virtual</span><span style="color: #008000"> </span><span style="color: #008000">Machine</span><span style="color: #008000"> </span><span style="color: #008000">Manager</span><span style="color: #008000"> </span><span style="color: #008000">Healthcheck</span><span style="color: #008000"> 
.</span><span style="color: #008000">VERSION</span><span style="color: #008000">
</span><span style="color: #008000">1</span><span style="color: #008000">.</span><span style="color: #008000">0</span><span style="color: #008000">
.</span><span style="color: #008000">DESCRIPTION</span><span style="color: #008000">
  </span><span style="color: #008000">Generates</span><span style="color: #008000"> </span><span style="color: #008000">a</span><span style="color: #008000"> </span><span style="color: #008000">HTML</span><span style="color: #008000"> </span><span style="color: #008000">Healthcheck</span><span style="color: #008000"> </span><span style="color: #008000">report</span><span style="color: #008000"> 
.</span><span style="color: #008000">NOTES</span><span style="color: #008000">
  </span><span style="color: #008000">Author</span><span style="color: #008000">(</span><span style="color: #008000">s</span><span style="color: #008000">): </span><span style="color: #008000">Ivo</span><span style="color: #008000"> </span><span style="color: #008000">Beerens</span><span style="color: #008000"> 
.</span><span style="color: #008000">EXAMPLE</span><span style="color: #008000">
  </span><span style="color: #008000">PS</span><span style="color: #008000">> ./</span><span style="color: #008000">scvmmhc</span><span style="color: #008000">.</span><span style="color: #008000">ps1</span><span style="color: #008000">
#></span><span style="color: #000000">

</span><span style="color: #008000"># Import modules
</span><span style="color: #5f9ea0">Import-Module</span><span style="color: #000000"> </span><span style="color: #5f9ea0">-Name</span><span style="color: #000000"> </span><span style="color: #800000">"Hyper-v"</span><span style="color: #000000">
</span><span style="color: #5f9ea0">Import-Module</span><span style="color: #000000"> </span><span style="color: #5f9ea0">-Name</span><span style="color: #000000"> </span><span style="color: #800000">"VirtualMachineManager"</span><span style="color: #000000">

</span><span style="color: #008000">#Variables
</span><span style="color: #800080">$Date</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Get-Date</span><span style="color: #000000">
</span><span style="color: #800080">$Datefile</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> ( </span><span style="color: #5f9ea0">get-date</span><span style="color: #000000"> )</span><span style="color: #000000">.</span><span style="color: #8b4513">ToString</span><span style="color: #000000">(</span><span style="color: #800000">'</span><span style="color: #800000">yyyy-MM-dd-hhmmss</span><span style="color: #800000">'</span><span style="color: #000000">)
</span><span style="color: #800080">$File</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">New-Item</span><span style="color: #000000"> </span><span style="color: #5f9ea0">-type</span><span style="color: #000000"> </span><span style="color: #0000ff">file</span><span style="color: #000000"> </span><span style="color: #800000">"D:\Temp\Healtcheck_$datefile.html"</span><span style="color: #000000">

</span><span style="color: #008000">#Connect to the SCVMM server
</span><span style="color: #0000ff">Clear</span><span style="color: #000000">
</span><span style="color: #800080">$VMMName</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Read-Host</span><span style="color: #000000"> </span><span style="color: #800000">"Enter System Center Virtual Machine Server Name to check"</span><span style="color: #000000">
</span><span style="color: #5f9ea0">Write-Host</span><span style="color: #000000"> </span><span style="color: #800000">"VMM name is $VMMName"</span><span style="color: #000000"> </span><span style="color: #5f9ea0">-ForeGround</span><span style="color: #000000"> </span><span style="color: #0000ff">Red</span><span style="color: #000000"> 
</span><span style="color: #5f9ea0">Get-VMMServer</span><span style="color: #000000"> </span><span style="color: #5f9ea0">-ComputerName</span><span style="color: #000000"> </span><span style="color: #800080">$VMMName</span><span style="color: #000000">

</span><span style="color: #008000">#HTML
# Add Text to the HTML file 
</span><span style="color: #000000">
</span><span style="color: #0000ff">Function</span><span style="color: #000000"> </span><span style="color: #0000cd">Create-HTMLTable
</span><span style="color: #000000">    {
    </span><span style="color: #0000ff">param</span><span style="color: #000000">([</span><span style="color: #0000ff">array</span><span style="color: #000000">]</span><span style="color: #800080">$Array</span><span style="color: #000000">)
    </span><span style="color: #800080">$arrHTML</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #800080">$Array</span><span style="color: #000000"> </span><span style="color: #0000ff">|</span><span style="color: #000000"> </span><span style="color: #5f9ea0">ConvertTo-Html</span><span style="color: #000000">
    </span><span style="color: #800080">$arrHTML</span><span style="color: #000000">[</span><span style="color: #ff0000">-</span><span style="color: #000000">1</span><span style="color: #000000">] </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #800080">$arrHTML</span><span style="color: #000000">[</span><span style="color: #ff0000">-</span><span style="color: #000000">1</span><span style="color: #000000">]</span><span style="color: #000000">.</span><span style="color: #8b4513">ToString</span><span style="color: #000000">()</span><span style="color: #000000">.</span><span style="color: #8b4513">Replace</span><span style="color: #000000">(</span><span style="color: #800000">'</span><span style="color: #800000"></body></html></span><span style="color: #800000">'</span><span style="color: #000000">,</span><span style="color: #800000">""</span><span style="color: #000000">)
    </span><span style="color: #0000ff">Return</span><span style="color: #000000"> </span><span style="color: #800080">$arrHTML</span><span style="color: #000000">[</span><span style="color: #000000">5</span><span style="color: #000000">.</span><span style="color: #000000">.2000</span><span style="color: #000000">]
    }

</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #000000">@</span><span style="color: #000000">()
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><html><head></head><body></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> 
</span><span style="color: #000000">'<</span><span style="color: #0000ff">style</span><span style="color: #000000">></span><span style="color: #0000ff">table</span><span style="color: #000000">{</span><span style="color: #0000ff">border</span><span style="color: #ff0000">-</span><span style="color: #0000ff">style</span><span style="color: #000000">:</span><span style="color: #0000ff">solid;border</span><span style="color: #ff0000">-</span><span style="color: #0000ff">width</span><span style="color: #000000">:1</span><span style="color: #0000ff">px;font</span><span style="color: #ff0000">-</span><span style="color: #0000ff">size</span><span style="color: #000000">:8</span><span style="color: #0000ff">pt;background</span><span style="color: #ff0000">-</span><span style="color: #0000ff">color</span><span style="color: #000000">:</span><span style="color: #008000">#ccc;width:100%;}th{text-align:left;}td{background-color:#fff;width:20%;border-style:so
</span><span style="color: #0000ff">lid;border</span><span style="color: #ff0000">-</span><span style="color: #0000ff">width</span><span style="color: #000000">:1</span><span style="color: #0000ff">px;</span><span style="color: #000000">}</span><span style="color: #0000ff">body</span><span style="color: #000000">{</span><span style="color: #0000ff">font</span><span style="color: #ff0000">-</span><span style="color: #0000ff">family</span><span style="color: #000000">:</span><span style="color: #0000ff">verdana;font</span><span style="color: #ff0000">-</span><span style="color: #0000ff">size</span><span style="color: #000000">:12</span><span style="color: #0000ff">pt;</span><span style="color: #000000">}</span><span style="color: #0000ff">h1</span><span style="color: #000000">{</span><span style="color: #0000ff">font</span><span style="color: #ff0000">-</span><span style="color: #0000ff">size</span><span style="color: #000000">:12</span><span style="color: #0000ff">pt;</span><span style="color: #000000">}</span><span style="color: #0000ff">h2</span><span style="color: #000000">{</span><span style="color: #0000ff">font</span><span style="color: #ff0000">-</span><span style="color: #0000ff">size</span><span style="color: #000000">:10</span><span style="color: #0000ff">pt;</span><span style="color: #000000">}</span><span style="color: #000000"><</span><span style="color: #ff0000">/</span><span style="color: #0000ff">style</span><span style="color: #000000">>'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><h1>Hyper-V health check</h1></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><h1>Versie 1.0</h1></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><h2>Date and time</h2></span><span style="color: #800000">'</span><span style="color: #000000">,</span><span style="color: #800080">$date</span><span style="color: #000000">

</span><span style="color: #008000"># Hosts
</span><span style="color: #800080">$HVHosts</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Get-VMHost</span><span style="color: #000000"> </span><span style="color: #0000ff">|</span><span style="color: #000000"> </span><span style="color: #0000ff">Select</span><span style="color: #000000"> </span><span style="color: #0000ff">HostCluster</span><span style="color: #000000">,</span><span style="color: #0000ff">Name</span><span style="color: #000000">,</span><span style="color: #0000ff">PhysicalCPUCount</span><span style="color: #000000">,</span><span style="color: #0000ff">CoresPerCPU</span><span style="color: #000000">,</span><span style="color: #0000ff">ProcessorManufacturer</span><span style="color: #000000">,</span><span style="color: #0000ff">CPUSpeed</span><span style="color: #000000">,</span><span style="color: #0000ff">CPUModel</span><span style="color: #000000">,@</span><span style="color: #000000">{</span><span style="color: #0000ff">N</span><span style="color: #ff0000">=</span><span style="color: #800000">"Memory(GB)"</span><span style="color: #0000ff">;E</span><span style="color: #ff0000">=</span><span style="color: #000000">{[</span><span style="color: #0000ff">math</span><span style="color: #000000">]</span><span style="color: #000000">::</span><span style="color: #8b4513">Round</span><span style="color: #000000">(((</span><span style="color: #000080">$_</span><span style="color: #000000">.</span><span style="color: #8b4513">TotalMemory</span><span style="color: #000000">)</span><span style="color: #ff0000">/</span><span style="color: #000000">1</span><span style="color: #0000ff">GB</span><span style="color: #000000">)</span><span style="color: #000000">,</span><span style="color: #000000">3</span><span style="color: #000000">)}}</span><span style="color: #000000">,</span><span style="color: #0000ff">OperatingSystem</span><span style="color: #000000">,</span><span style="color: #0000ff">EnableLiveMigration</span><span style="color: #000000">,</span><span style="color: #0000ff">VMHostGroup</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><p></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><h1>Hosts</h1></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><p></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Create-HTMLTable</span><span style="color: #000000"> </span><span style="color: #800080">$HVHosts</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"></p></span><span style="color: #800000">'</span><span style="color: #000000"> 

</span><span style="color: #008000"># VM
</span><span style="color: #800080">$VMs</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Get-VM</span><span style="color: #000000"> </span><span style="color: #0000ff">|</span><span style="color: #000000"> </span><span style="color: #0000ff">Select</span><span style="color: #000000"> </span><span style="color: #0000ff">Name</span><span style="color: #000000">,</span><span style="color: #0000ff">ComputerName</span><span style="color: #000000">,</span><span style="color: #0000ff">HostName</span><span style="color: #000000">,</span><span style="color: #0000ff">CPUCount</span><span style="color: #000000">,</span><span style="color: #0000ff">CpuType</span><span style="color: #000000">,</span><span style="color: #0000ff">MemoryAssignedMB</span><span style="color: #000000">,</span><span style="color: #0000ff">DynamicMemoryEnabled</span><span style="color: #000000">,</span><span style="color: #0000ff">OperatingSystem</span><span style="color: #000000">,</span><span style="color: #0000ff">HasVMAdditions</span><span style="color: #000000">,</span><span style="color: #0000ff">VMAddition</span><span style="color: #000000">,</span><span style="color: #0000ff">VirtualMachineState</span><span style="color: #000000">,</span><span style="color: #0000ff">Status</span><span style="color: #000000">,</span><span style="color: #0000ff">ReplicationStatus</span><span style="color: #000000">,</span><span style="color: #0000ff">Location</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><p></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><h1>VMs</h1></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><p></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Create-HTMLTable</span><span style="color: #000000"> </span><span style="color: #800080">$VMs</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"></p></span><span style="color: #800000">'</span><span style="color: #000000">

</span><span style="color: #008000"># Snapshots
</span><span style="color: #800080">$VMSnaps</span><span style="color: #000000"> </span><span style="color: #ff0000">=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Get-VM</span><span style="color: #000000"> </span><span style="color: #0000ff">|</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Get-VMCheckpoint</span><span style="color: #000000"> </span><span style="color: #0000ff">|</span><span style="color: #000000"> </span><span style="color: #0000ff">Select</span><span style="color: #000000"> </span><span style="color: #0000ff">VM</span><span style="color: #000000">,</span><span style="color: #0000ff">Name</span><span style="color: #000000">,</span><span style="color: #0000ff">Description</span><span style="color: #000000">,</span><span style="color: #0000ff">AddedTime</span><span style="color: #000000">,</span><span style="color: #0000ff">ModifiedTime</span><span style="color: #000000"> 
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><p></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><h1>Snapshots</h1></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"><p></span><span style="color: #800000">'</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Create-HTMLTable</span><span style="color: #000000"> </span><span style="color: #800080">$VMSnaps</span><span style="color: #000000">
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"></p></span><span style="color: #800000">'</span><span style="color: #000000">

</span><span style="color: #008000"># End
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #ff0000">+=</span><span style="color: #000000"> </span><span style="color: #800000">'</span><span style="color: #800000"></body></html></span><span style="color: #800000">'</span><span style="color: #000000">    
</span><span style="color: #800080">$output</span><span style="color: #000000"> </span><span style="color: #0000ff">|</span><span style="color: #000000"> </span><span style="color: #5f9ea0">Out-File</span><span style="color: #000000"> </span><span style="color: #800080">$file</span><span style="color: #000000"> </span><span style="color: #5f9ea0">-Force</span><span style="color: #000000">

</span><span style="color: #008000"># Open the HTML file
</span><span style="color: #0000ff">ii</span><span style="color: #000000"> </span><span style="color: #800080">$file</span>
```

The script can be easily extended with other checks, for example an e-mail option. If you have other additions let me know so the script can be extended.

</body></html>
