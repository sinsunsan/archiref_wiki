## Liens 

http://www.selectorweb.com/grep_tutorial.html
## Cas pratiques

* **Only the files**    
Retrieve only the files in which the string is found whatever the number of instance in this file   
```grep -rl "my string```

* **Exclude dir**   
Chercher dans les fichiers mais pas dans les fichiers binaires (images...)   
```grep -rn "petite question" * --exclude-dir='files'```

* **Escape special character**   
Echapper les caractère spéciaux    
<pre>grep -rn "\$vars\\['comment'\]" * --exclude-dir="files"</pre>

* **Grep on the files searched by find**
* Search in a specific file   
```find -type f -name *rue89block.inc* -exec grep "3 voix" {} \;```

* Search in all .install files the pattern "nodequeue"
```find -type f -name *.install -exec grep -rn nodequeue {} \;```

* **Escape special character** (here regular expression)
<pre>```grep -rn "\\['options'\\]\\['status'\\]"```</pre>

To search ['option']['status'] typical drupal form array   