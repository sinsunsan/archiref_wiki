### iptables rules explanation

* http://www.thegeekstuff.com/2011/06/iptables-rules-examples/

### How to log iptables 
http://www.thegeekstuff.com/2012/08/iptables-log-packets/


Example of a log
```
May  7 20:44:44 Ubuntu-1404-trusty-64-minimal kernel: [545448.996144] iptables denied: IN=eth0 OUT= MAC=44:8a:5b:29:e8:c9:3c:61:04:71:0f:98:08:00 SRC=82.224.93.129 DST=148.251.68.173 LEN=64 TOS=0x00 PREC=0x00 TTL=48 ID=30884 DF PROTO=TCP SPT=51667 DPT=80 WINDOW=65535 RES=0x00 SYN URGP=0
```

From http://www.thegeekstuff.com/2012/08/iptables-log-packets/

> In the above output:

> IPTables-Dropped: This is the prefix that we used in our logging by specifying –log-prefix option
> IN=em1 This indicates the interface that was used for this incoming packets. This will be empty for outgoing packets
> OUT=em1 This indicates the interface that was used for outgoing packets. This will be empty for incoming packets.
> SRC= The source ip-address from where the packet originated
> DST= The destination ip-address where the packets was sent to
> LEN= Length of the packet
> PROTO= Indicates the protocol (as you see above, the 1st line is for outgoing ICMP protocol, the 2nd line is for incoming TCP protocol)
> SPT= Indicates the source port
> DPT= Indicates the destination port. In the 2nd line above, the destination port is 443. This indicates that the incoming HTTPS packets was dropped


### ubuntu ressource on iptables 
https://help.ubuntu.com/community/IptablesHowTo

### How to list iptables open ports 
``` iptables -L ```
Or a more verbose version 
```iptables --line -vnL```


### Restart iptables service 

``` service iptables restart```

### how to open the 80 port
http://www.binarytides.com/open-http-port-iptables-centos/

### ufw uncomplicated firewall ubuntu 
https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server

### Export available iptables rules
```iptables-save```


### Problem of blocking ssh access whiling wanting to clear the rules [not solved]
* http://serverfault.com/questions/619530/iptables-f-locks-me-out-of-the-server-until-reboot-why 
