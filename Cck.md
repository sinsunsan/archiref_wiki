* **Update a cck field**   

Way the nodereference count module save its data into its fields

* **content_database_info**     
Retrieve infos on how the field is store in database 
http://drupalcontrib.org/api/drupal/contributions%21cck%21content.module/function/content_database_info/6
````
  $count = nodereference_count_get_count($field, $nid);
  $db_info = content_database_info($field);
  $table = $db_info['table'];
  $column = $db_info['columns']['value']['column'];

  $update = new stdClass();
  $update->vid = $vid;
  $update->nid = $nid;
  $update->$column = $count;
  drupal_write_record($table, $update, 'vid');
````

* **drupal_write_record**   
http://api.drupal.org/api/drupal/includes%21common.inc/function/drupal_write_record/6   
Record datas in the database according to a schema. 
