http://www.lullabot.com/articles/how-install-memcache-debian-etch   
http://codelikezell.com/how-to-install-memcached-on-centos/


First, install the dependency libevent:   
http://www.geeksww.com/tutorials/operating_systems/linux/installation/how_to_install_libevent_on_debianubuntucentos_linux.php   

http://blog.loicg.net/how-to/installation-memcached-ubuntu-server/
```
  cd /usr/local/src
  curl -O http://monkey.org/~provos/libevent-1.4.14b-stable.tar.gz
  tar xzvf libevent-1.4.14b-stable.tar.gz 
  cd libevent-1.4.14b-stable
 ./configure --prefix=/opt/libevent
  make && make install
```