* **#required**
In drupal 7 it's no more an element. We need to write 
$form['form_state']['#redirect'] to make the redirection


* **#redirect don't exist more in d7**
I've tested    
$form_state['#redirect'] = 'admin/comment/avertir1/3193886';   
but this second element is more powerful   
$form['#action'] = check_plain(request_uri()); 

* **#ajax**   
Make an ajax call to replace an existing element    
http://api.drupal.org/api/drupal/includes--ajax.inc/group/ajax
  