* **field_info_field**    
http://api.drupal.org/api/drupal/modules!field!field.info.inc/function/field_info_field/7   
Retrieve a field object in the language it'll be displayed (d7)   
For exemple we have loaded a $term object, and we want the field object of one of its fields. 
```
$position = field_get_items('taxonomy_term', $term, 'field_term_position');
```

* **Get field language code** 
Recupérer un champs sans se préoccuper des codes de langues(und ...)
solution qui semble la plus simple
```
$taxonomy_major = field_get_items('node', $node, 'field_taxonomy_main', $node->language);
```

Autres solutions un peu moins simple
```
$lang = field_language('node', $node, 'field_taxonomy_main');
$term_major = $node->field_taxonomy_main[$lang][0]['tid'];
```
