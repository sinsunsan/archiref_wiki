* **function_exists**   
Check if a function is defined before to call it (and to prevent an error if it doesn't exist   

http://php.net/function_exists


* **func_get_args**

http://fr2.php.net/func_get_args   

Permet de récupérer les arguments qui ont été passé dans la fonction sous la forme d'un tableau.
S'utilise donc à l'intérieur d'une fonction. 
```
function drupal_get_form($form_id) {
  $form_state = array();

  $args = func_get_args();
  // Remove $form_id from the arguments.
  array_shift($args);
  $form_state['build_info']['args'] = $args;

  return drupal_build_form($form_id, $form_state);
}
```