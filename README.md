# munin-linksys-cpuload
Munin plugin for monitoring Cisco Linksys SG300 series CPU load

## Uses following OIDs:

* .iso.org.dod.internet.mgmt.mib-2.system.sysDescr.0 = STRING: SG300-52 52-Port Gigabit Managed Switch
* .iso.org.dod.internet.private.enterprises.9.6.1.101.1.7.0 = INTEGER: 2
* .iso.org.dod.internet.private.enterprises.9.6.1.101.1.8.0 = INTEGER: 23
* .iso.org.dod.internet.private.enterprises.9.6.1.101.1.9.0 = INTEGER: 8

## Usage (for Debian Buster):
 edit `/etc/munin/plugin-conf.d/snmp_communities` and add:

    snmp_switch1.sw.example.com_*
    env.community your_RO_SNMP_password

 shell:

    cd /etc/munin/plugins
    ln -s /usr/local/bin/snmp__linksys_load snmp_switch1.sw.example.com_linksys_load
    service munin-node restart
