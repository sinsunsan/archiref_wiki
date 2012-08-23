Don't need to pass the whole $form variable
But intead pass by reference th sub array that we care about 
```php
<?php
function rue89_common_toggled_element_default_value(&$element, $name, $default_value) {
  $element['#after_build'][] = 'rue89_common_toggled_element_after_build';
  $element['#pre_render'][] = 'rue89_common_toggled_element_pre_render';
  $element['#toggle_value'] = $default_value;
  $element['#element_name'] = $name;
}
?>
```

And the function call in the hook_form_alter function 
```php
<?php
$form['submitted']['photo_name']['#theme_wrappers'] = array('rue89_common_form_element');
    $form['submitted']['photo_name']['#attributes']['class'] = array('tf', 'clearfocus', 'default', 'rounded3');
    rue89_common_toggled_element_default_value($form['submitted']['photo_name'], 'name', t('Votre nom'));

?>
```