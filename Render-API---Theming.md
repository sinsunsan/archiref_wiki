### Références 

* Slides on d7 render API

### API

* **hook_theme**   
http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_theme/7   
Main hook to define how a renderable array are going to be rendered

* **drupal_render**   
http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_render/7   
Transform a structured array in a rendered array with html to display. 
Called by render() wrapper function

* **drupal_html_class**   
http://api.drupal.org/api/drupal/includes!common.inc/function/drupal_html_class/7   
Prepare a string to be used as a class (replace _ by - ...)   


* **field_attach_view**   
http://api.drupal.org/api/drupal/modules!field!field.attach.inc/function/field_attach_view/7    
Return an renderable array of the given field 

### Pages 

* [[preprocess]]
* [[customize user register page]]

### Liens 

* Using the theme layer    
http://drupal.org/node/933976

* The hook_theme to declare template   
http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_theme/7

* Theming search results    
http://api.drupal.org/api/drupal/modules!search!search-result.tpl.php/6

* View theming with template   
http://drupal.org/node/352970