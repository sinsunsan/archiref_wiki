* **Elements of ajax validation**   
See http://drupalconnect.com/blog/drupal-ajax-form-validation

1.  a form define in the .module
1.  in this form definition, drupal_add_js to add the validation javascript
1.  in the js file, make a jquery listener, that call an url in ajax 
1.  the url is defined in a hook menu and point to a callback function. 
1.  depending of the reponse the js part print a message to the user
