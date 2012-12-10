### Query in drupal 7

Drupal 7 introduce a new abstraction layer that allow to make a query to different types of database 

All syntax are explained in this page :   
http://drupal.org/node/310075

Liste of database related API function   
http://drupal.org/node/150223

**Exemples**
<pre> 
  $query = db_select('unitag', 'u');
  $query->leftJoin('node', 'n', 'u.nid = n.nid');
  $query->fields('u', array('utid', 'nid', 'vid', 'field', 'name', 'basename'))  ;
  $result = $query->execute();
</pre>

* **drupal_install_schema**   
http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_install_schema/7   
Install the databse defined by a hook_schema
  