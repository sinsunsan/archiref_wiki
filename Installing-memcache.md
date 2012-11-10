http://blog.loicg.net/how-to/installation-memcached-ubuntu-server/

```
// Pour procéder à l’installation de memcached (une version de memcache), nous allons installer les packages suivants :
// memcached (le principal intéressé ^^)
// php-pear (car nous aurons besoin de pecl)
// php5-dev (pour son précieux phpize)
// libmemcached-dev (pour obtenir la librairie memcached.o)

sudo apt-get install memcached php-pear php5-dev libmemcached-dev

// Ensuite, nous installons memcache depuis la librairie pecl
sudo pecl install Memcache

// Puis, nous activons la librairie PHP memcache :
sudo echo "extension=memcache.so" > /etc/php5/apache2/conf.d/memcache.ini
// Nous ajoutons la ligne suivante dans le fichier de configuration de PHP (/etc/php5/apache2/php.ini), qui nous permet de définir la stratégie relative aux hashs.
memcache.hash_strategy="consistent"
// Il est maintenant temps de lancer le démon de memcached :
memcached -d -m 2048 -l 10.0.0.40 -p 11211
//Et pour finir, on relance Apache :
/etc/init.d/apache2 restart

```