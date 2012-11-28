### Références 

* Slides on d7 render API http://fr.slideshare.net/frandoh/the-render-api-in-drupal-7

### API

* **theme function**   
http://api.drupal.org/api/drupal/includes%21theme.inc/function/theme/7   
Central function in the theming process
Serve as a router to call the right callback function define in hook_theme. The first argument is the name of the theme hook to be used, the second the renderable array to render.   
There is two way to render, theme function of template. If the render will be made by a template, there is a preprocess phase that prepare variables that will be available in the templates. 


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
* **override core or contributed module css**      
No need to write ani css rules, create a css file with the same name as the original css file to override and declare it in .info file of your theme   
http://drupal.org/node/263967 

* Using the theme layer    
http://drupal.org/node/933976

* The hook_theme to declare template   
http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_theme/7

* Theming search results    
http://api.drupal.org/api/drupal/modules!search!search-result.tpl.php/6

* View theming with template   
http://drupal.org/node/352970