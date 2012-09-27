## Liens 

http://www.selectorweb.com/grep_tutorial.html
## Cas pratiques

* Retrieve only the files in which the string is found whatever the number of instance in this file   
```grep -rl "my string```

* Chercher dans les fichiers mais pas dans les fichiers binaires (images...)   
```grep -rn "petite question" * --exclude-dir='files'```

* Echapper les caractère spéciaux    
```grep -rn "\$vars\['comment']" * --exclude-dir="files"```

* Grep on the files searched by find 
``` find -type f -name *rue89block.inc* -exec grep "3 voix" {} \; ```

* Escape special character (here regular expression)
```grep -rn "\['options'\]\['status'\]"```

To search ['option']['status'] typical drupal form array   