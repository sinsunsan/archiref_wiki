# Technique de debugage

Lister tous les hook appelé par drupal 
dans drupal 7
includes/modules.inc


* Lullabot post that explain how to backtrace when an error occure
http://www.lullabot.com/articles/quick-and-dirty-debugging


## Lister les différents hook appelés

Changer la fonction d'invocation des hooks
situés 
includes/module.inc:815:function module_invoke_all($hook) {


``` php
<?php 
function module_invoke_all($hook) {
  $args = func_get_args();
  // Remove $hook from the arguments.
  unset($args[0]);
  $return = array();
  foreach (module_implements($hook) as $module) {
    $function = $module . '_' . $hook;
    
    // Debug function 
    if (function_exists('dsm') && function_exists('user_access')) dsm($module . ' - ' . $hook);

    if (function_exists($function)) {
      $result = call_user_func_array($function, $args);
      if (isset($result) && is_array($result)) {
        $return = array_merge_recursive($return, $result);
      }
      elseif (isset($result)) {
        $return[] = $result;
      }
    }
  }

  return $return;
}
?>
```

## Lister les appels de fonction (backtrace)
```
print "<pre>";
print_r(debug_backtrace());
print "</pre>";
```
To print the calling function without the arguments passsed from function to function 
```
print "<pre>";
print_r(debug_backtrace(DEBUG_BACKTRACE_IGNORE_ARGS));
print "</pre>";
```


## Debug the user_access function 

Display the permission string return FALSE   
```
if (!$perm[$account->uid][$string]){print_r($string . '<br>');}
```

