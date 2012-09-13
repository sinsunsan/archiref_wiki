### Attach fields to display them

* **field_attach_prepare_view**   
http://api.drupal.org/api/drupal/modules!field!field.attach.inc/function/field_attach_prepare_view/7   
Allow to modify field before display


* **entity_prepare_view**    
http://api.drupal.org/api/drupal/includes%21common.inc/function/entity_prepare_view/7   
Useful when an object is entity is called inside another entity

* **field_attach_view**    
http://api.drupal.org/api/drupal/modules!field!field.attach.inc/function/field_attach_view/7   
Return of a renderable array

Exemple of the use of this 3 functions in https://gist.github.com/40e049c86061a114cfde

* **field_default_view**    
http://api.drupal.org/api/drupal/modules!field!field.default.inc/function/field_default_view/7Function       called when the field is viewed and transform it into a renderable array 

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