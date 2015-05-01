nmap -p 80 example.com

Allow to say if a given port is open or not

* List all open port
```
netstat -tulnp
```
* Show if iptables port is open 
```
iptables -L
```
* Test a specific port from outside 
```
telnet www.openbricks.io 80
```