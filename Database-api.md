### Simple drupal 6 query 

Very important 
**Good syntax**
```
$sql = 'SELECT * FROM {node} LIMIT 1,30';
$query = db_query($sql);
while ($row = db_fetch_array($query)) {

}

* **EntityFieldQuery** Class to make request on entities
https://api.drupal.org/api/drupal/includes!entity.inc/class/EntityFieldQuery/7

```
**Wrong syntax**
Always the same first row (because it redo the query again and again
```
$sql = 'SELECT * FROM {node} LIMIT 1,30';
while ($row = db_fetch_array(db_query($sql)) {

}
```
 while ($row = db_fetch_array($query)) {

### Query in drupal 7

Drupal 7 introduce a new abstraction layer that allow to make a query to different types of database 

All syntax are explained in this page :   
http://drupal.org/node/310075

Liste of database related API function   
http://drupal.org/node/150223

Schema API to define the array that describe the schema of the database    
http://api.drupal.org/api/drupal/includes%21database%21schema.inc/group/schemaapi/7

**Exemples**
```
<?php
  $query = db_select('unitag', 'u');
  $query->leftJoin('node', 'n', 'u.nid = n.nid');
  $query->fields('u', array('utid', 'nid', 'vid', 'field', 'name', 'basename'))  ;
  $result = $query->execute();
```
Short syntax, with chaining methods
db_select return an object, and each method return the modified object
```
<?php
// Create an object of type SelectQuery and directly 
// add extra detail to this query object: a condition, fields and a range
$query = db_select('users', 'u')
  ->condition('u.uid', 0, '<>')
  ->fields('u', array('uid', 'name', 'status', 'created', 'access'))
  ->range(0, 50);
?>
```
* **drupal_install_schema**   
http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_install_schema/7   
Install the database defined by a hook_schema

* **Debugging the SQL Query**
To examine the SQL query that the query object will build at a particular point in its lifecycle, call its __toString() method:
```
<?php
  print_r($query->__toString());
?>
```

Don't work for me use    
 dpm($result->getQueryString());   
But I've got stille some placeholder, and not the plain sql query

* **hook_schema**   
http://api.drupal.org/api/drupal/modules%21system%21system.api.php/function/hook_schema/7   
Hook schema allow to define a schema for a given module. 
When using drupal_install_schema and drupal_get_schema_unprocessed we get the module schema, it means all the database tables that could be defined here. We don't call a specific table definition.

* **hook_install**   
The database creation happen only at first install when the module is enabled and disabled, this hook isn't called 


  