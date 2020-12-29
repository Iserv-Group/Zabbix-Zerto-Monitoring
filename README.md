# Zabbix-Zerto-Monitoring
This is a fork of the template, [Zerto Replication VPG monitoring for vSphere](https://share.zabbix.com/virtualization/zerto-replication-vpg-monitoring-for-vsphere), found on Zabbix share. Please reference the original share for installation instructions.

## Changes
### Adding Sub Status's
The major change on this template from the original is adding Sub Status's from Zerto to decrease false alarms for sites that have frequent large delta changes. I created a new alert with high priority that filters out sub status's that are typically transient. I also created a medium priority trigger that alerts if a VPG is not meeting the SLA for 4 or more hours and made it dependent on the other new alert. Finally, I lowered the severity of the trigger for a VPG that simply isn't meeting it's SLA and made it dependent on both of the alerts above.
