### Query in drupal 7

<pre> 
  $query = db_select('unitag', 'u');
  $query->leftJoin('node', 'n', 'u.nid = n.nid');
  $query->fields('u', array('utid', 'nid', 'vid', 'field', 'name', 'basename'))  ;
  $result = $query->execute();
</pre>