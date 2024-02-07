---
author: Ivo Beerens
categories:
- Uncategorized
date: "2023-09-22T09:22:37Z"
guid: https://www.ivobeerens.nl/?p=9027
id: 9027
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
title: Download the latest Hashicorp Terraform, Packer, and Vault bits
url: /2023/09/22/download-the-latest-hashicorp-terraform-packer-and-vault-bits/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

I created a PowerShell Script that downloads the latest version of Terraform, Packer, and Vault, extracts the archives to binaries, and adds the folder of the path environment variable. Running this script ensures you always work with the latest versions of Terraform, Packer, and Vault.

```powershell  
<#  
 .DESCRIPTION Function to download and extract the latest Packer, Terraform and Vault version from Hashicorp  
 .NOTES Author: Ivo Beerens  
 .NOTES Site: www.ivobeerens.nl  
 .NOTES Version: 1.0  
 .NOTES Changed: September 10, 2023  
 .NOTES Reason: Creation  
\#>

\#Enable TLS 1.2  
\[Net.ServicePointManager\]::SecurityProtocol = \[Net.SecurityProtocolType\]::Tls12  
\#Speed up the Invoke-Webrequest command  
$ProgressPreference = ‘SilentlyContinue’

\#Variables  
$temp\_folder = "c:\\install\\" #Temp download location  
$hashicorp\_destination = "c:\\install\\hashicorp\\" #Path for storing the Hashicorp binaries

\#Check if the temp folder exists  
If(!(test-path -PathType container $hashicorp\_destination )) {  
 New-Item -ItemType Directory -Path $hashicorp\_destination  
}

\#Jump to the download folder  
Set-Location $hashicorp\_destination

Function Download-Hashicorp {  
 param (  
 \[string\]$product,  
 \[string\]$url  
 )  
 try {  
 Write-Host "………… Download $product from Hashicorp …………" -ForegroundColor Green  
 $urls = Invoke-WebRequest -Uri $url| Select-Object -Expand links | Where-Object href -match "//releases\\.hashicorp\\.com/$product/\\d.\*/$product\_.\*\_windows\_amd64\\.zip$" | Select-Object -Expand href  
 $filename = $urls | Split-Path -Leaf  
 $download = $temp\_folder + $filename  
 #Download Hashicorp bits  
 Invoke-WebRequest $urls -outfile $download  
 #Expand archive  
 Write-Host "………… Expand $product archive to binary …………" -ForegroundColor Yellow  
 Expand-Archive $download -DestinationPath $hashicorp\_destination -Force  
 Write-Host "………… Remove $product archive download…………" -ForegroundColor Blue  
 #Remove download  
 Remove-Item $download  
 }  
 catch {  
 Write-Host "An error occurred while downloading or extracting $product" -ForegroundColor Red  
 throw $\_.Exception.Message  
 }  
 }

\#Download Packer, Vault, and Terraform  
$products = @{  
 ‘packer’ = ‘https://developer.hashicorp.com/packer/downloads’  
 ‘vault’ = ‘https://developer.hashicorp.com/vault/downloads’  
 ‘terraform’ = ‘https://developer.hashicorp.com/terraform/downloads’  
}

foreach ($product in $products.GetEnumerator()) {  
 Download-Hashicorp -product $product.Name -url $product.Value  
}

\##Add the Hashicorp binary folder to the system environment variable path  
Write-Host "………… Add folder to path …………" -ForegroundColor Green  
\[Environment\]::SetEnvironmentVariable("PATH", $Env:PATH + ";" + $hashicorp\_destination, \[EnvironmentVariableTarget\]::User)  
Write-Host "Please restart your PowerShell session for the changes to take effect." -ForegroundColor Yellow  
```

**Line 15**: Change the temp folder for storing the downloaded archive files  
**Line 16:** Change the folder path for storing the Hashicorp binaries for Terraform, Packer, and Vault  
**Line 19-22:** Check if the folder for storing the Hashicorp binaries for Terraform, Packer, and Vault exists. If not it will be created  
**Line 24-50**: Function that downloads and extracts the archive files for Terraform, Packer, and Vault  
**Line 52-61**: Run the function to download and extract the Hashicorp Terraform, Packer, and Vault  
**Line 63-66**: adds the folder of the Hashicorp binaries to the path environment variable

The latest version of this script can be found on my GitHub page, [Link.](https://github.com/ibeerens/Powershell/blob/master/Hashicorp-Downloads.ps1)
