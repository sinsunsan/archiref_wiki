### HOOKS

* **hook_menu_alter**   
http://api.drupal.org/api/drupal/modules!system!system.api.php/function/hook_menu_alter/7   
Allow to modify a menu defined by another module

* **hook_menu_link_alter**   
http://api.drupal.org/api/drupal/modules!system!system.api.php/function/hook_menu_link_alter/7   
Allow to modify a menu link defined by another module
This hook is fired when a menu item get saved
All the available keys are http://api.drupal.org/api/drupal/includes%21menu.inc/function/menu_link_save/7

* **hook_path_insert**  
https://api.drupal.org/api/drupal/modules!path!path.api.php/function/hook_path_insert/7   
Do something when a new path is being created (like aliasing for example)   

* **drupal_set_breadcrumb**     
https://api.drupal.org/api/drupal/includes!common.inc/function/drupal_set_breadcrumb/7    
Define an array of page starting at home and to the parent of the current page
```
if ($node->type === "video_type" && $view_mode === "full") {
        $breadcrumb = array();
        $breadcrumb[] = l('Accueil', '<front>');
        $breadcrumb[] = l('Videos', 'videos');
        drupal_set_breadcrumb($breadcrumb);
    }
```
Good tuto in french    
http://juliendubreuil.fr/drupal/breadcrumb-personnalise

### API functions

* **menu_get_item()**    
Get the current menu item the page we are on, and retrieve information about the router, callback    
http://api.drupal.org/api/drupal/includes%21menu.inc/function/menu_get_item/6

* **menu_get_object()**   
Return the object we are on, a node if a node page or a user if a user page   
http://api.drupal.org/api/drupal/includes!menu.inc/function/menu_get_object/6   
Use example : http://drupalcode.org/project/page_title.git/blob/1d3944636a0c6afd4065e8f552eddb0f9d8ffbed:/modules/node.page_title.inc

* **menu_tree()**   
Return a menu tree replace % by their value for exemple user/% by user%45
http://api.drupal.org/api/drupal/includes!menu.inc/function/menu_tree/7   

* **menu_execute_active_handler**   
https://api.drupal.org/api/drupal/includes!menu.inc/function/menu_execute_active_handler/6   
Execute the callback associated with the current menu item

### Tricks

* **How to get the url/uri of the current page**   
http://www.devdaily.com/drupal/theme-how-get-uri-current-drupal-page   
http://drupal.org/node/27732

* **To return the full url with ? and aliased path**    
```
global $base_root;
$vars['feed_url'] = $base_root . request_uri();
```