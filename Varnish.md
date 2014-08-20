* Check varnish syntax    
http://codepoets.co.uk/2011/checking-varnish-configuration-syntax/

* Regular expression for varnish    
http://docs.fastly.com/guides/21835572/31252953    
http://kly.no/varnish/regex.txt


````
Regular expression cheat sheet for Varnish

Varnish regular expressions are NOT case sensitive. Varnish uses POSIX
regular expressions, for a complete guide, see: "man 7 regex"

Basic matching:
	req.url ~ "searchterm"
	True if req.url contains "searchterm" anywhere.

	req.url == "searchterm"
	True if req.url is EXACTLY searchterm

Matching at the beginning or end of a string
	req.http.host ~ "^www."
	True if req.http.host starts with "www" followed by any single
	character.

	req.http.host ~ "^www\."
	True if req.http.host starts with "www.". Notice that . was
	escaped.

	req.url ~ "\.jpg$"
	True if req.url ends with ".jpg"

Multiple matches
	req.url ~ "\.(jpg|jpeg|css|js)$"
	True if req.url ends with either "jpg", "jpeg", "css" or "js".

Matching with wildcards
	req.url ~ "jp.g$"
	True if req.url ends with "jpeg", "jpag", "jp$g" and so on, but NOT
	true if it ends with "jpg".

	req.url ~ "jp.*g$"
	True if req.url ends with "jpg", "jpeg", "jpeeeeeeeg",
	"jpasfasf@@!!g" and so forth (jp followed by 0 or more random
	characters ending with the letter 'g').

Conditional matches
	req.url ~ "\.phg(\?.*)?$"
	True if req.url ends with ".php" ".php?foo=bar" or ".php?", but not
	".phpa". Meaning: Either it ends with just ".php" or ".php"
	followed by a question mark any any number of characters.

	req.url ~ "\.[abc]foo$"
	True if req.url ends with either ".afoo" ".bfoo" or ".cfoo".

	req.url ~ "\.[a-c]foo$"
	Same as above.

Replacing content
	set req.http.host = regsub(req.http.host, "^www\.","");
	Replaces a leading "www." in the Host-header with a blank, if
	present.

	set req.http.x-dummy = regsub(req.http.host, "^www.","leading-3w.");
	Sets the x-dummy header to contain the host-header, but replaces
	a leading "www." with "leading-3w" example:

	Host: www.example.com => 
		Host: www.example.com
		X-Dummy: leading-3w.example.com

	Host: example.com =>
		Host: example.com
		X-Dummy: example.com
````

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
http://andrewdunkle.com/how-install-varnish-drupal-7

Restart both service after a vcl change 
```
sudo service apache2 restart
sudo service varnish restart
```

Working vcl for varnish 3 
http://drupal.org/node/1196916#comment-4660760

Need to copy the content of secret file in drupal varnish admin