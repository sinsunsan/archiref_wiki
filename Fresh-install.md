* **lamp stack**

```
// Lamp    
sudo apt-get install apache2 php5 mysql-server libapache2-mod-php5 php5-mysql

// Php my admin (escape data auto config)   
apt-get install phpmyadmin

// Error when connecting 
// The mcrypt extension is missing. Please check your PHP configuration.

sudo apt-get install php5-mcrypt
sudo /etc/init.d/apache2 restart


`````

Activation of mod_rewrite    
http://www.apache-mod-rewrite.fr/verification-installation-mod-rewrite
```
ln -s /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled/rewrite.load
service apache2 restart
```

Install Curl (facebook module drupal)
```
apt-get install php5-curl
/etc/init.d/apache2 restart
```



* **common used executable**

```
// Git version manager
apt-get install git 

// Vim command line text editor
apt-get install vim 
```

* **ssh keys access**

* **enable smartd for disk monitoring**  
http://doc.ubuntu-fr.org/smartmontools   
```  
apt-get install smartmontools
```

* **copy www and import db**

* **Memcache**

http://www.lullabot.com/articles/installing-memcached-redhat-or-centos

// Installation fo chkconfig used in lullabot tuto
apt-get install chkconfig

http://loginroot.com/ubuntu-12-04-64bit-sbininsserv-no-such-file-or-directory/
```
chkconfig -s ssh on
// /sbin/insserv: No such file or directory

// Fix is simple, just to add symlink:
ln -s /usr/lib/insserv/insserv /sbin/insserv

// In the problem errors while trying to install memcache as a service
```

* **PECL install**   

```
// Install of pecl
apt-get install php-pear

// Install of make (compilator)
apt-get install make

// Install memcache through PECL
pecl install memcache

// Edit php.info 
vim /etc/php5/apache2/php.ini
```

* **cron**   
```
crontab -e
```

* **drupal**   
Drush   
http://drupal.org/project/drush   

```
// Drush (pear install) 
pear channel-discover pear.drush.org
pear install drush/drush

```