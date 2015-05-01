* Initialisation 

### User management 

* Change root PAssword 
```
passwd root
```
* Create your user user 
```
adduser newuser
```
* Add your user in the sudoers 
```
sudo adduser <username> sudo
```
* Initialize apt-get database
```
apt-get update
```

### MYSQL 

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-remote-database-to-optimize-site-performance-with-mysql

Open mysql port for a different server
http://www.cyberciti.biz/tips/linux-iptables-18-allow-mysql-server-incoming-request.html

***

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

```

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

* **security**    
http://www.alsacreations.com/tuto/lire/622-Securite-firewall-iptables.html

* **[[add a user account]]**

* [[Bash not sourced problem]]

### Installation of node.js 

* Node Js
````
apt-get install nodejs
````
* NPM
````
apt-get install npm
````
Debug installation node
* http://stackoverflow.com/questions/26320901/cannot-install-nodejs-usr-bin-env-node-no-such-file-or-directory

* Forever
https://github.com/foreverjs/forever
