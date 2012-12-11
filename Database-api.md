### Query in drupal 7

Drupal 7 introduce a new abstraction layer that allow to make a query to different types of database 

All syntax are explained in this page :   
http://drupal.org/node/310075

Liste of database related API function   
http://drupal.org/node/150223

Schema API to define the array that describe the schema of the database    
http://api.drupal.org/api/drupal/includes%21database%21schema.inc/group/schemaapi/7

**Exemples**
<pre> 
  $query = db_select('unitag', 'u');
  $query->leftJoin('node', 'n', 'u.nid = n.nid');
  $query->fields('u', array('utid', 'nid', 'vid', 'field', 'name', 'basename'))  ;
  $result = $query->execute();
</pre>

* **drupal_install_schema**   
http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_install_schema/7   
Install the database defined by a hook_schema


* **hook_schema**   
http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_schema/7   
Hook schema allow to define a schema for a given module. 
When using drupal_install_schema and drupal_get_schema_unprocessed we get the module schema, it means all the database tables that could be defined here. We don't call a specific table definition.

* **hook_install**   
The database creation happen only at first install when the module is enabled and disabled, this hook isn't called 


  