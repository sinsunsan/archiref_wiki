* **Elements of ajax validation**
See http://drupalconnect.com/blog/drupal-ajax-form-validation


* a form define in the .module
* in this form definition, drupal_add_js to add the validation javascript
* in the js file, make a jquery listener, that call an url in ajax 
* the url is defined in a hook menu and point to a callback function. 
* depending of the reponse the js part print a message to the user

