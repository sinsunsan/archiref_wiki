* **drupal_process_form**   
Make the form processing   
Could be called by the classic [drupal_get_form] (http://api.drupal.org/api/drupal/includes%21form.inc/function/drupal_build_form/7) or it is an ajax call [ajax_form_callback](http://api.drupal.org/api/drupal/includes%21ajax.inc/function/ajax_form_callback/7)
http://api.drupal.org/api/drupal/includes%21form.inc/function/drupal_process_form/7

* **drupal_get_form**   
Render a form with a given form_id, this function does not allow to pass value to the form 
In the signature of the function there is only $form_id and not $form_state
Is calling drupal_build_form
http://api.drupal.org/api/drupal/includes%21form.inc/function/drupal_get_form/7

* **drupal_build_form**   
Render a form and a $form_state array could be given 
http://api.drupal.org/api/drupal/includes%21form.inc/function/drupal_build_form/7