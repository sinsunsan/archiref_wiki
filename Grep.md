## Liens 

http://www.selectorweb.com/grep_tutorial.html


## Cas pratiques

* Chercher dans les fichiers mais pas dans les fichiers binaires (images...)   
<pre>
grep -rn "petite question" * --exclude-dir='files'` 
</pre>

* Echapper les caractère spéciaux    
<pre>
grep -rn "\$vars\['comment']" * --exclude-dir="files"
</pre>

* Grep on the files searched by find 
<pre>
find -type f -name *rue89block.inc* -exec grep "3 voix" {} \;
</pre>

* Escape special character (here regular expression)
```
grep -rn "\['options'\]\['status'\]"
```
To search ['option']['status'] typical drupal form array   
