Submit a form programmaticaly in d7   
http://brianfisher.name/content/programmatically-submit-form-drupal-7

To generate the form, it's easyer to dump the array with var_export
var_export($form_state['build_info']['args'][0]);

* **drupal_form_submit** (d7)   
http://api.drupal.org/api/drupal/includes!form.inc/function/drupal_form_submit/7

* **form_load_include**   
Make sur the inc file in wich a form can be defined before to work on it    
http://api.drupal.org/api/drupal/includes%21form.inc/function/form_load_include/7