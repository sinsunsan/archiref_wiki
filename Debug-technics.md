* **mix of print_r and d custom function that add a die and other stuff**
The behavior is different than dpm because it's printed on the script page and not on the following one. 
the d() function is here https://gist.github.com/4060502

Lister tous les hook appelé par drupal 
dans drupal 7
includes/modules.inc


* **Integrate backtrace to drupal_set_message**    
Lullabot post that explain how to backtrace when an error occure
http://www.lullabot.com/articles/quick-and-dirty-debugging


* **Lister les différents hook appelés**
Changer la fonction d'invocation des hooks situés 
includes/module.inc:815:function module_invoke_all($hook) {
Code on gist https://gist.github.com/7ae97f626eb1629aaa38

* **Lister les appels de fonction (backtrace)**
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

* **Debug the user_access function**   
Display the permission string return FALSE   
```
if (!$perm[$account->uid][$string]){print_r($string . '<br>');}
```

* **How to know a template is being used**
Just place a d('are you in used');
If it's in used, a white screen will show with this message 

* **Recursion in not the end dpm**   
When using devel, it occure that a element is shown as recursion. 
To see what's inside, make an other dpm with only this sub element key 
For exemple 
if writing ``dpm($form)``
you see
``$form['view']`` show recursion 

you can write write ``dpm($form['view']);``
to see what's inside

* **Difference between debuging function in php** var_dump , var_export , print_r   
http://stackoverflow.com/questions/5039431/difference-between-var-dump-var-export-print-r

* **Output all defined variables**   
When in a template and we don't know which variables are defined in this context, we can use a php function 
**get_defined_vars** 
http://php.net/manual/en/function.get-defined-vars.php

* **debug an auto complete**   
An autocomplete don't retrieve node's title we expected, just change it to select list to see what's are available choices

* **debug the creation of a db schema**    
The schema is installed only for the first installation of a module. 
So If it does'nt pass the first time, it's necessary to disable + install the module 
And then reinstall it. A trick could be to call drupal_install_schema function from a hook init so you can debug database installation without doing those boring steps

* **know that a function pass by there**    
put small message output with d() function that break execution
https://gist.github.com/4060502 

* **Debug the SQL query drupal is actually doing after all the abastraction layers has been passed**   
Set the devel module to display the queries and find yours
Easier 
```
$result = db_query("SELECT 'name' from {taxonomy_term_data} WHERE 'tid' IN (" . implode(',' , $tid) . ")");
dpm($result);
```