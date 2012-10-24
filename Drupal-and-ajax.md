1. Ajax call in a javascript files : 
1. Hook_menu to define a callback function and an url of the ajax call 
```
  $items['system/ajax/rue89/user'] = array(
    'type' => MENU_CALLBACK,
    'page callback' => 'rue89_platform_users_ajax_callback',
    'delivery_callback' => 'rue89_platform_users_ajax_callback',
    'access arguments' => array('access content'),
    'file' => 'rue89_platform_users.pages.inc',
  );
```
1. Callback function that return a JSON object


### Exemples

* **Add an ajax behavior to a form element**
```php
  $form['actions']['submit']['#ajax'] = array(

    'callback' => 'rue89_platform_users_ajax_user_login_callback',
    'wrapper' => 'modal_content',
    'method' => 'replace',
    'progress' => array('type' => 'hidden'),
    'path' => 'system/ajax/rue89/user/register'
  );
```

### Ressources 
* Drupal 7 and ajax on drupal.org    
http://drupal.org/node/752056