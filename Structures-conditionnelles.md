* **Tester à la fois qu'une variable à une valeur et qu'elle existe** 

Cette syntaxe ne produira pas d'erreurs même si la clé field_taxonomy_minor n'existe pas dans l'objet node
<pre>
if (isset($node->field_taxonomy_minor) && $node->field_taxonomy_minor){
</pre>


* **Structure ternaire**

Exemple de codes

In the two following example the variable is tested and assigned if it exists
<pre>
$replacements[$original] = $sanitize ? check_plain($text) : $text;
</pre>
```
$qr = isset($content['field_i3v_qr']['#items'][0]['node']) ? $content['field_i3v_qr']['#items'][0]['node'] : NULL;
```
