## Mysql

* **[[Mysql data types]]**
* **[[Mysql command examples]]**
* **[[Mysql Repair]]**
* **[[Mysql agregate function]]**

### Liens Tuto 

* Good install tuto  https://www.linode.com/docs/databases/mysql/how-to-install-mysql-on-ubuntu-14-04
http://www.pantz.org/software/mysql/mysqlcommands.html    

* How to debug to socket error (can't find the socket)    
http://www.tech-recipes.com/rx/762/solve-cant-connect-to-local-mysql-server-through-socket-tmpmysqlsock/


***

### Importation d'un dump de base de donnée pour synchroniser version dev de archiref

<code>
mysqldump -u UTILISATEUR -p MOTDEPASSE BASEDEDONNEES < backup041118.sql
</code>



Permet de créer une nouvelle table de base de donnée utilisable par l'utilisateur dba_user et qui s'appelle test_site_database 
<code>
mysqladmin -u dba_user -p create test_site_database 
</code>

Permet de copier une base de données vers une autre sans faire un dump, c'est à dire sans écrire un fichier texte plus rapide. 
<code>
mysqldump --opt --user=<user> --password=<password> <original database> | mysql --user=<user> --password=<password> <new database>
</code>

MySQL : Copier facilement une base de données vers un autre serveur
Publié le 3 juillet 2008 par jmfontaine
Il arrive parfois d’avoir besoin de copier une base de données vers un autre serveur. Il est possible de faire facilement cette opération en utilisant l’outil mysqldump en ligne de commande :

<code>
mysqldump table_source | mysql --host=hote -C table_cible
</code>

<h3>Les dumps de base de données</h3>
A noter en ne mettant pas de mot de passe mais avec l'option -p on peut rentrer le mote de passe en mode interactif

***

### Creer un dump de base de donnée
<code>
mysqldump -u UTILISATEUR -p MOTDEPASSE BASEDEDONNEES > backup041118.sql
</code>

***

### Restaurer un dump  
<code>
mysqldump -u UTILISATEUR -p MOTDEPASSE BASEDEDONNEES < backup041118.sql
</code>

Avec la commande mysql essayé marche
 
<code>
mysql -h localhost -u sqledi -p password < EdiPublicit-2012-01-05T17-00-08.mysql
</code>

http://www.cyberciti.biz/faq/import-mysql-dumpfile-sql-datafile-into-my-database/   
```
mysql -u username -p -h localhost DATA-BASE-NAME < data.sql
````

Il est également possible de créer la copie sur le même serveur en omettant l’option –host :
<code>
mysqldump table_source | mysql -C table_cible
</code>

* **Restore a dump from a gunzip file**    
gunzip < archiref-2013-01-01T23-56-21.mysql.gz | mysql -u root -p d6_archiref_prod

Pour installer mysqladmin sur Mac il faut créer un lien symbolique dans le repértoire  /usr/bin
<code>
sudo  ln -s /Applications/MAMP/Library/bin/mysqldump /usr/bin/mysqldump
sudo  ln -s /Applications/MAMP/Library/bin/mysqladmin /usr/bin/mysqladmin
sudo ln -s /Applications/MAMP/Library/bin/mysql /usr/bin/mysql 
</code>

***

### Transférer une table d'une machine à une autre
<code>
mysqldump -u UTILISATEUR -p MOTDEPASSE BASEDEDONNEES | ssh utilisateur:motdepasse@15.156.125.32 "mysql BASEDEDONNEES2"
</code>

*** 

### Allow remote access to a mysql database server 

* http://www.cyberciti.biz/tips/how-do-i-enable-remote-access-to-mysql-database-server.html

### How to setup mysql loging 

* http://www.pontikis.net/blog/how-and-when-to-enable-mysql-logs
