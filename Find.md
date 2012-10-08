### Applatir une structure de fichier

<pre>
find . -type f -exec mv {} dest \;
</pre>
Explication pas à pas 

* On recherche tous les fichiers
* Sur chaque fichier on execute la commande mv avec les paramètres trouvés {}  
* \; signifie la fin de l'execution
*

### Compter le nombre de fichier dans un repertoire contenant des sous-repertoires

<pre>
find images_archiref1 -type f | wc -l
</pre>

### Tous les répértoires qui contienne le nom 'rss'

<pre>
find -type d -name rss
</pre>

### Nombre de fichiers se terminant par ".jpg"

<pre>
find -type f -name "*.jpg" | wc -l
</pre>

### Inverser les patterns, les fichiers qui n'ont pas le pattern spécifié

<pre>
find -type f ! -name "*.jpg" | wc -l
</pre>

### Renommer des fichiers 

<pre>
find . -name '*.swf' -exec mv {} {}.old \;
</pre>


### Delete directory older than 15 days and with copy in the name only in the root $dir 

````
find $dir -name "*copy*" -maxdepth 1 -type d -mtime +15 -exec rm -rv {} \;
````

### Delete temp files created by a configuration of vim
```
```

