### 1- Declare the page with hook_menu

```php
<?php 

/**
 * Implements hook_menu().
 */
function rue89_comments_menu() {
  $items['admin/comment/avertir/%comment'] = array(
    'title' => 'Warn',
    'access callback' => 'user_access',
    'access arguments' => array('administer comments'),
    'page callback' => 'rue89_comments_avertir',
    'page arguments' => array(3),
    'type' => MENU_CALLBACK
  );
}

?>
```

### 2- Declare a theme function / template

http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_theme/7

* **path**: Override the path of the file to be used. Ordinarily the module or theme path will be used, but if the file will not be in the default path, include it here. This path should be relative to the Drupal root directory.   

* **file**: The file the implementation resides in. This file will be included prior to the theme being rendered, to make sure that the function or preprocess function (as needed) is actually loaded; this makes it possible to split theme functions out into separate files quite easily.    

* **render element**: (see above) The name of the renderable element or element tree to pass to the theme function. This name is used as the name of the variable that holds the renderable element or tree in preprocess and process functions.  
    
* **template**: If specified, this theme implementation is a template, and this is the template file without an extension. Do not put .tpl.php on this file; that extension will be added automatically by the default rendering engine (which is PHPTemplate). If 'path', above, is specified, the template should also be in this path.   
```php
<?php

/**
 * Implements hook_theme().
 */
function rue89_comments_theme($existing, $type, $theme, $path) {
  $base = array(
    'path' => drupal_get_path('module', 'rue89_comments') . '/theme',
    'file' => 'theme.inc'
  );
  return array(
    'rue89_comments_avertir_form' => array(
      'render element' => 'form',
      'template' => 'avertir-form',
    ) + $base,
    'rue89_comments_avertir_window' => array(
      'variables' => array(),
      'template' => 'comment-avertir-window',
    ) + $base,

  );
}

?>
```

### 3- Write the callback function 

The call back function   
It take this argument defined in hook menu,   
process them and call the theme function / template throught the function theme   
http://api.drupal.org/api/drupal/includes%21theme.inc/function/theme/7

The call function have as first argument the theme hook defined in hook_theme. 
The use of theme function allow you to override this value, by defing a hook_theme_alter

```php
<?php

/**
 * Avertir callback function.
 */
function rue89_comments_avertir($comment) {
  if ($comment) {
    $form = render(drupal_get_form('rue89_comments_avertir_form', $comment));
    $author = rue89_common_username($comment->uid);
    return theme('rue89_comments_avertir_window', array('alert_form' => $form, 'author' => $author));
  }
  else {
    return drupal_not_found();
  }
}

?>
```


### 4- Define the form

```php
<?php

function rue89_comments_avertir_form($form, &$form_state, $comment) {
 // a standard form api form 
 $form['flag']['user_yellowflag'] = array(
    '#type' => 'checkbox',
    '#title' => $user_warning_text,
    '#default_value' => $user_warning_text,
    '#attributes' => $user_warning_checked,
  );
  $form['flag']['user_block'] = array(
    '#type' => 'checkbox',
    '#title' => t('Block this user'),
    '#default_value' => t('Block this user'),
    '#attributes' => $user_status_checked,
  );
 // ....
 $form['submit'] = array(
    '#type' => 'submit',
    '#value' => t('Send a warning email'),
    '#weight' => 10,
  );
  return $form;
}

?>
```