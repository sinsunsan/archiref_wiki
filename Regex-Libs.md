### **Twitter user name**
````
(?<=^|(?<=[^a-zA-Z0-9-_\\.]))@([A-Za-z]+[A-Za-z0-9_]+)
````

http://shahmirj.com/blog/extracting-twitter-usertags-using-regex

### **Twitter hashtag**
````
/\B#\w*[a-zA-Z]+\w*/
````
http://erictarn.com/post/1060722347/the-best-twitter-hashtag-regular-expression

### ?
<pre>
 if (preg_match('@^(?:http://)?([^/]+)(\/swf\/)([^/]+)@i', $params['source'] , $matches)) {
    $params['id'] = $matches[3];
 }
</pre>


### **Reconnaître les urls courtes de daily motion**
<pre>@dai\.ly/([^\?"\&]+)@i</pre>
le . est échappé grace à \

### **Trouver simplement un mot contenu dans une chaîne**   
<pre>preg_match('#href#', $string1 , $matches);</pre>

### **Commence par (^---) ou se termine par (---$)**   
``preg_match('#^<a href="|a>$#', $string1 , $matches);``

### **Lettre qui se répètent**    
``#bor?is# Boris avec 1 r ou 2``

### **Récupérer le id du commentaire d'une url**

Le html du lien à analyser
``
<a href="http://dev.v2.seb.dev89.com:8080/2012/04/06/le-bobo-repoussoir-de-la-droite-puis-ennemi-prefere-de-le-pen-230350#comment-3005312" class="title">
Le « bobo », repoussoir de la droite puis ennemi préféré de Le Pen
</a>
``
La regex
`
preg_match('@^<a href="([^"]*)(#comment-)(\d+)@i', $string1 , $matches);
`

### **twitter tweet url**
```
#href="https://twitter.com/([^/]+)/status/([0-9]+)#
https://twitter.com/drupalplanet/status/248414059467251713
array (
  0 => 'href="https://twitter.com/Dries/status/248397811220115456',
  1 => 'Dries',
  2 => '248397811220115456',
)

```