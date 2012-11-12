* Make custom view handler   
http://www.ericschaefer.org/blog/2011/01/09/custom-field-handlers-for-views-2-drupal

* **hook_views_data**    
http://api.drupal.org/api/views/docs!docs.php/function/hook_views_data/6   
Allow to define the data of our new table to view, allow to define  relationship, fields...   
Exemple in asset module (a custom module used by rue89)
https://gist.github.com/e01a52eaf5f70fe0f65e

* **views_embed_view**
http://api.drupal.org/api/views/views.module/function/views_embed_view/7   
Embed a view in everything (blocks, node....)   

The relationship handler   
http://api.drupal.org/api/views/handlers%21views_handler_relationship.inc/class/views_handler_relationship/6

### code example

* **use a view to list content in a autocomplete function**   



