* **Change a module's weight**   
Can change it with a hook install    
https://gist.github.com/3705680

* **Define a hook**   
Exemple in the menu attributes module that retrieve other attributes not yet implemented by the module author.
https://gist.github.com/3705709

* **Define a hook and and create an API file**   
When the module define a hook , it need to illustrated it's usage by creating a modulename.api file 
Like this one for menu attributes module https://gist.github.com/3705693

* **hook_install**   
When to do at the module install time. If the module manage a table, it'll implement here 
[drupal_install_schema](http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_install_schema/7)