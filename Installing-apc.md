http://dev.petitchevalroux.net/php/optimiser-son-serveur-installation-apc-php.123.html
http://blog.thecodingmachine.com/fr/content/installer-le-cache-dop-code-apc-sur-ubuntu-1004

```
// Install a useful library
aptitude install libpcre3-dev

// Install APC
pecl install apc


```

add 
extension=memcache.so
to /etc/php5/apache/php.ini

and
```
service apache2 restart
```

