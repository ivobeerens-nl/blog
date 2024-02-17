---
title: ""
date: "2014-05-21T11:01:22.000Z"
---

\[code language="PowerShell"\] Get-VMMManagedComputer | select Name, State, Role, AgentVersion \[/code\]

\[code language="PowerShell"\] Get-VM | Select Name, VirtualMachineState, HasVMAdditions, VMAddition | Out-GridView \[/code\]

\[code language="PowerShell"\] Get-VM | Where-Object {$\_.VMAddition -notlike "6.3.9600.16384" -and ($\_.VirtualMachineState -eq "Running")} | FT Name,VMAddition \[/code\]

Create a text file servers.csv

\[code language="PowerShell"\] "Name" "server1" "server2" \[/code\]

\[code language="PowerShell"\] Import-Module VirtualMachineManager $ADCs = Import-csv c:\\scripts\\servers.csv foreach ($DC in $ADCs ) { $Sessid = New-Pssession $DC.Name Write-Host " " Write-host $DC.name -ForegroundColor Green Write-Host " " Invoke-Command -Session $Sessid -ScriptBlock {powercfg -LIST} } \[/code\]
