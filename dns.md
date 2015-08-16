# DNS

### RHEL
`/etc/sysconfig/network-scripts/ifcfg-eth${INTERFACE}`

`DHCP_HOSTNAME=hostname`

### Debian
`/etc/dhcp3/dhclient.config`

`send host-name "hostname"`


##### Misc
* Script ????
```
#!/bin/sh
ADDR=`/sbin/ifconfig eth0 | grep 'inet addr' | awk '{print $2}' | sed -e s/.*://`
HOST=`hostname -f`
echo "update delete $HOST A" > /var/nsupdate
echo "update add $HOST 86400 A $ADDR" >> /var/nsupdate
nsupdate /var/nsupdate
```
