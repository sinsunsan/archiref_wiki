La fonction de validation par défaut est form_id_validate 
D'autre part son nom est visible dans la clef $form['#validate']

Exemple of validation function
https://gist.github.com/6b17f7ed0c6b9e06142a

* **How to change a value in a validation function**

http://drupal.org/node/542796   
http://www.rahulsingla.com/blog/2010/02/drupal-changing-form-field-values-in-validationsubmit-handlers
http://buildamodule.com/video/drupal-7-development-core-concepts-how-to-build-and-manipulate-forms-with-the-form-api-using-validation-functions


in fact we need only to change $form['values']['field_name']['und'][0]['value']
``` $form_state['values']['field_asset_tweet']['und'][0]['value'] = $matches[1];```


* **form_set_value**   
http://api.drupal.org/api/drupal/includes%21form.inc/function/form_set_value/7   
Change the value of a form element