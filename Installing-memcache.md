http://www.lullabot.com/articles/how-install-memcache-debian-etch   
http://codelikezell.com/how-to-install-memcached-on-centos/


First, install the dependency libevent:   
```
  cd /usr/local/src
  curl -O http://monkey.org/~provos/libevent-1.4.14b-stable.tar.gz
  tar xzvf libevent-1.4.14b-stable.tar.gz 
  cd libevent-1.4.14b-stable
  ./configure --prefix=/usr/local
  make && make install
```
