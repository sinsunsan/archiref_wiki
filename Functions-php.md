### htmlentities 
http://php.net/manual/en/function.htmlentities.php   
Convert special characters '" & ... into their html entities equivalent

### html_entity_decode
http://php.net/manual/en/function.html-entity-decode.php   
The contrary of htmlentities, remove unwanted &quot;walk&quot; the &lt;b&gt;dog&lt;

### strstr
http://php.net/manual/en/function.strstr.php   
Chercher un bout de chaine dans une chaine 

### microtime
http://php.net/manual/fr/function.microtime.php   
Afficher un timestamp

### list
http://php.net/manual/fr/function.list.php   
Permet d'assigner en un seul appel des valeurs à plusieurs variables 

<pre>
$info = array('coffee', 'brown', 'caffeine');

// Liste toutes les variables
list($drink, $color, $power) = $info;
echo "$drink is $color and $power makes it special.\n";
</pre>

### die
Interrompt un script php 

<pre>
die();
</pre>


