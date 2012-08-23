### field_info_field   
Retrieve info about a given field (d7)   
http://api.drupal.org/api/drupal/modules!field!field.info.inc/function/field_info_field/7

### Get field language code
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