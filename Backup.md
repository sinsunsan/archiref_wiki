https://wiki.archlinux.org/index.php/Full_System_Backup_with_rsync

## Allow root login only with key auth and from one ip

http://serverfault.com/questions/189574/allow-root-login-from-one-ip-address-only

* Edit sshd_config (usually in /etc/ssh), and add or change the following directives

```
 PermitRootLogin yes
  AllowUsers root@thehosttoallow
```

* Then restart the daemon

```
  service ssh restart

```

PermitRootLogin without-password

Marche mais il faut rajouter root dans allow user

* Configure the sshd  
http://www.faqs.org/docs/securing/chap15sec122.html

