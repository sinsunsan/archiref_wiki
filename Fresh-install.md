* Initialisation 

### [User management](Server-Install#user--password)

* **Initialize apt-get database**
```
apt-get update
```

### MYSQL 

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-remote-database-to-optimize-site-performance-with-mysql

Open mysql port for a different server
http://www.cyberciti.biz/tips/linux-iptables-18-allow-mysql-server-incoming-request.html

***

### [Install LAMP (Apache + Mysql + Php)

// Php my admin (escape data auto config)   
apt-get install phpmyadmin

* **copy www and import db**

* [[Installing APC]]

* [[Installing memcache]]

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

* **bashr & vim**   
https://github.com/sinsunsan/dotvim   
https://github.com/sinsunsan/bashrc

* **drupal**   
Drush   
http://drupal.org/project/drush   

```
// Drush (pear install) 
pear channel-discover pear.drush.org
pear install drush/drush

```
If the system don't know about drush make a symlink between it's current location ans /usr/local/bin, it means drush must be a symlink as 
/usr/local/bin/drush linking to its actual location (home folder, or elsewhere)

****

### Securisation of the server 

* **security**    
http://www.alsacreations.com/tuto/lire/622-Securite-firewall-iptables.html

* Log iptables fail rules
````
sudo iptables -I INPUT 5 -m limit --limit 5/min -j LOG --log-prefix "iptables denied: " --log-level 7
````

### [Installation of node.js](Server-Install#node) 


### Misc 

* **[[add a user account]]**

* [[Bash not sourced problem]]
