---
author: Ivo Beerens
categories:
- VMware
date: "2018-03-06T15:17:31Z"
guid: https://www.ivobeerens.nl/?p=5460
id: 5460
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- vcsa
title: Top vCenter Server Appliance (VCSA) troubleshooting commands
url: /2018/03/06/top-vcenter-server-appliance-vcsa-troubleshooting-commands/
---

During the configuration and troubleshooting of vCenter Server Appliances (VCSA) I maintain a list of commands that I frequently use. This list contains my top configuration and troubleshooting VCSA commands:

- Enable access the Bash shell:

\[code language=”text”\]  
shell.set –enabled true  
```

- Permanently configure the default Shell to BASH for Root:

\[code language=”text”\]  
chsh -s /bin/bash root  
```

- Log location of the VCSA:

\[code language=”text”\]  
/var/log/vmware/vsphere-client/logs/  
```

- VCSA service management:

\[code language=”text”\]  
Check status  
service-control –status –all  
List services  
service-control –list  
Stop all services  
service-control –stop –all  
Start all services  
service-control –start –all  
```

- Join the AD domain from PSC:

\[code language=”text”\]  
/opt/likewise/bin/domainjoin-cli join domain.nl aduser password  
```

After the AD domain join reboot the appliance

- Check the AD domain join status:

\[code language=”text”\]  
/opt/likewise/bin/domainjoin-cli query  
```

- Leave AD domain join:

\[code language=”text”\]  
/opt/likewise/bin/domainjoin-cli leave  
```

After the AD domain leave reboot the appliance

- Certificate Manager location:

\[code language=”text”\]  
/usr/lib/vmware-vmca/bin/certificate-manager  
```

- Test port connectivity from the VCSA:

\[code language=”text”\]  
curl -v telnet://target ip address:port  
Example:  
curl –v telnet://mypsc.domain.local:443  
```

- Identity which PSC the VCSA is pointing to:

\[code language=”text”\]  
/usr/lib/vmware-vmafd/bin/vmafd-cli get-ls-location –server-name localhost  
```

- Repoint the VCSA to another PSC:

\[code language=”text”\]  
cmsso-util repoint –repoint-psc "PSC01"  
```

- Check the PSC replication partner:

\[code language=”text”\]  
/usr/lib/vmware-vmdir/bin/vdcrepadmin -f showpartners -h localhost -u administrator -w password  
```

- Check the PSC replication status:

\[code language=”text”\]  
/usr/lib/vmware-vmdir/bin/vdcrepadmin -f showpartnerstatus -h localhost -u administrator -w password  
```

Output:

\[code language=”text”\]  
Partner: psc02  
Host available: Yes  
Status available: Yes  
My last change number: 4274  
Partner has seen my change number: 4274  
Partner is 0 changes behind.  
```

- VDC Admin tool test LDAP and force replication

\[code language=”text”\]  
/usr/lib/vmware-vmdir/bin/vdcadmintool  
```
