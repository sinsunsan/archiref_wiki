### Linux

nmap -p 80 example.com

Allow to say if a given port is open or not

* **List all open port**
```
netstat -tulnp
```
* **Show if iptables port is open**
```
iptables -L
```
* **Test a specific port from outside**
```
telnet www.openbricks.io 80
```

* **how to log iptables**
http://www.thegeekstuff.com/2012/08/iptables-log-packets


### MAC 

* http://superuser.com/questions/597398/no-idea-what-is-listening-on-port-80-in-os-x
sudo lsof -i ':80'