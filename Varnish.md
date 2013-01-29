http://erikwebb.net/comment/8241

http://www.lullabot.com/articles/varnish-multiple-web-servers-drupal

Change all files from 8080 to 80
Uninstall varnish
```
perl -pi -e 's/\**:8080/\*:80/g' /etc/apache2/sites-available/*
perl -pi -e 's/Listen 8080$/Listen 80/g' /etc/apache2/ports.conf
perl -pi -e 's/\*:8080$/\*:80/g' /etc/apache2/ports.conf
service varnish stop
service apache2 restart
```

Change all files from 80 to 8080
Install varnish
```
perl -pi -e 's/\**:80/\*:8080/g' /etc/apache2/sites-available/*
perl -pi -e 's/Listen 80$/Listen 8080/g' /etc/apache2/ports.conf
perl -pi -e 's/\*:80$/\*:8080/g' /etc/apache2/ports.conf
service apache2 restart
service varnish start
```