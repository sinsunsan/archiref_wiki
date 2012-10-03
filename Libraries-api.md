How to add a js stored in the library dir   
http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_get_path/7#comment-13414

Exemple with modernizr
```
<?php
drupal_add_js(libraries_get_path('modernizr') . '/js/modernizr-1.6.min.js', array('group' => JS_THEME, 'every_page' => TRUE));
?>
```

* **libraries_get_path**   
http://drupalcontrib.org/api/drupal/contributions!libraries!libraries.module/function/libraries_get_path/6