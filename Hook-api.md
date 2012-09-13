# Fonctions liées aux hooks

* **drupal_alter**   
http://api.drupal.org/api/drupal/includes%21module.inc/function/drupal_alter/7   
Special function to create a hook of type hook_hooktype_alter 

* **module_invoke**   
http://api.drupal.org/api/drupal/includes!module.inc/function/module_invoke/7   
Fonction principale qui permet de créer un hook dans drupal. 
Il appelle les modules passés en arguments
```  module_invoke_all('entity_view', $asset, 'asset', $view_mode);```
In this exemple hook_entity_view will be called, with ther arguments $assets, 'asset', $view_mode
If we want to implement it we need to write a function called   
function mymodule_entity_view($asset, 'asset', $view_mode);

*  **module_implement**    
http://api.drupal.org/api/drupal/includes!module.inc/function/module_implements/7   
Retourne un array de modules qui implemente un hook donné