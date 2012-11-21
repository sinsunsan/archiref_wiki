### Query in drupal 7

Drupal 7 introduce a new abstraction layer that allow to make a query to different types of database 

All syntax are explaines in this page :   
http://drupal.org/node/310075

Exemples
<pre> 
  $query = db_select('unitag', 'u');
  $query->leftJoin('node', 'n', 'u.nid = n.nid');
  $query->fields('u', array('utid', 'nid', 'vid', 'field', 'name', 'basename'))  ;
  $result = $query->execute();
</pre>