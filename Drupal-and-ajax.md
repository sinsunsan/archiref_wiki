1. Ajax call in a javascript files : 
1. Hook_menu to define an url of the ajax call 
```
  $items['system/ajax/rue89/user'] = array(
    'type' => MENU_CALLBACK,
    'page callback' => 'rue89_platform_users_ajax_callback',
    'delivery_callback' => 'rue89_platform_users_ajax_callback',
    'access arguments' => array('access content'),
    'file' => 'rue89_platform_users.pages.inc',
  );
```