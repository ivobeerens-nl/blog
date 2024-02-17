---
title: "Top vCenter Server Appliance (VCSA) troubleshooting commands"
date: "2018-03-06T14:17:31.000Z"
categories: 
  - "vmware"
tags: 
  - "vcsa"
---

During the configuration and troubleshooting of vCenter Server Appliances (VCSA) I maintain a list of commands that I frequently use. This list contains my top configuration and troubleshooting VCSA commands:

- Enable access the Bash shell:

\[code language="text"\] shell.set --enabled true \[/code\]

- Permanently configure the default Shell to BASH for Root:

\[code language="text"\] chsh -s /bin/bash root \[/code\]

- Log location of the VCSA:

\[code language="text"\] /var/log/vmware/vsphere-client/logs/ \[/code\]

- VCSA service management:

\[code language="text"\] Check status service-control --status --all List services service-control --list Stop all services service-control --stop --all Start all services service-control --start --all \[/code\]

- Join the AD domain from PSC:

\[code language="text"\] /opt/likewise/bin/domainjoin-cli join domain.nl aduser password \[/code\]

After the AD domain join reboot the appliance

- Check the AD domain join status:

\[code language="text"\] /opt/likewise/bin/domainjoin-cli query \[/code\]

- Leave AD domain join:

\[code language="text"\] /opt/likewise/bin/domainjoin-cli leave \[/code\]

After the AD domain leave reboot the appliance

- Certificate Manager location:

\[code language="text"\] /usr/lib/vmware-vmca/bin/certificate-manager \[/code\]

- Test port connectivity from the VCSA:

\[code language="text"\] curl -v telnet://target ip address:port Example: curl –v telnet://mypsc.domain.local:443 \[/code\]

- Identity which PSC the VCSA is pointing to:

\[code language="text"\] /usr/lib/vmware-vmafd/bin/vmafd-cli get-ls-location --server-name localhost \[/code\]

- Repoint the VCSA to another PSC:

\[code language="text"\] cmsso-util repoint --repoint-psc "PSC01" \[/code\]

- Check the PSC replication partner:

\[code language="text"\] /usr/lib/vmware-vmdir/bin/vdcrepadmin -f showpartners -h localhost -u administrator -w password \[/code\]

- Check the PSC replication status:

\[code language="text"\] /usr/lib/vmware-vmdir/bin/vdcrepadmin -f showpartnerstatus -h localhost -u administrator -w password \[/code\]

Output:

\[code language="text"\] Partner: psc02 Host available: Yes Status available: Yes My last change number: 4274 Partner has seen my change number: 4274 Partner is 0 changes behind. \[/code\]

- VDC Admin tool test LDAP and force replication

\[code language="text"\] /usr/lib/vmware-vmdir/bin/vdcadmintool \[/code\]
