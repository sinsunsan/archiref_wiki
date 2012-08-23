* **drupal_get_forms**  
Allow to render a form, often used in hook menu at "page callbacks" key 
The first argument is the form_id. More arguments can be passed to the function. They will be passed to the form_builder.   
http://api.drupal.org/api/drupal/includes%21form.inc/function/drupal_get_form/7

* **drupal_build_form**   
The function called bu drupal_get_forms and render the form.    
http://api.drupal.org/api/drupal/includes%21form.inc/function/drupal_build_form/7

* **hook_forms**    
Allow to map a form function to different form id. Allow to have a base form, and variations of it 
If no callback function is found at the call of drupal_get_form, this function is called   
http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_forms/7