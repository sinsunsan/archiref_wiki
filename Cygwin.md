### Tutos

A complete html guide on cygwin   
http://cygwin.com/cygwin-ug-net/using.html

###  Concepts
* Cygwin create a full unix server inside the installation directory. 
* The default installation is at the root of windows. 
* all existing drive are accessible at /dir/cygdrive/c for drive c in windows. 
* all pwd in the cygwin directory, will be relative to this directory


### Permissions 

Cygwin permission, depends of what type of partition the hard drive has been formatted   
http://cygwin.com/cygwin-ug-net/using-filemodes.html


### Databases

* Connect to a Wamp databases, from Cygwin   
http://stackoverflow.com/questions/10995465/connecting-to-mysql-through-cygwin
```
 mysql -h 127.0.0.1 -u root -p
```
 works
To import a database dump for example 
```
 mysql -h 127.0.0.1 -u root -p database < /dir/dump.sql
```

```


