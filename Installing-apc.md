http://dev.petitchevalroux.net/php/optimiser-son-serveur-installation-apc-php.123.html
http://blog.thecodingmachine.com/fr/content/installer-le-cache-dop-code-apc-sur-ubuntu-1004

```
// Install a useful library
aptitude install libpcre3-dev

// Install APC
pecl install apc
```



create a file for apc configuration in conf.d
```
vim /etc/php5/apache2/conf.d
```

Paste the following code
```

;tweaks de la configuration d'aprés tuto 
; http://www.wikigento.com/optimisation-lampzendmagento/tuning-opcode-apc/

extension=apc.so


apc.ttl=7200
;par défaut 0
apc.user_ttl=7200
;par défaut 1
apc.shm_segments=3
;par défaut 30 soit 30MB de mémoire
;apc.shm_size=128
;Suite à première essai ou la mémoire était pleine on augmente
apc.shm_size=256
```

And restart apache
```
service apache2 restart

```

