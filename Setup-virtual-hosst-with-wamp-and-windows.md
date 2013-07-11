In c:/wamp/bin/apache/apache/Apache2.2.17/conf/extra/httpd-vhosts.conf
Add the new virtual hosts. 

```
NameVirtualHost auvergnelife-1-3.local
<VirtualHost *:80>
    ServerName auvergnelife-1-3.local
    ServerAlias *.auvergnelife-1-3.local
    DocumentRoot "C:\projets/auvergnelife-1.3"
    <Directory "C:\projets/auvergnelife-1.3">
        AllowOverride All
        Allow from All
    </Directory>
</VirtualHost>
```

In c:/windows/system32/drivers/etc/hosts
add the new localhosts
```
127.0.0.1 auvergnelife-1-3.local
```

Restart apache with wamp menu
