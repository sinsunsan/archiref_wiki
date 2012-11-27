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


```
$form['actions']['next'] = array(
  '#type' => 'submit',
  '#value' => t('Next step'),
  '#ajax' => array(
    'wrapper' => 'modal_content',
    // callback function used after the ajax request has return a result
    'callback' => 'rue89_platform_users_ajax_user_register_callback',
    // Progress throbber settings (in this case hidden)
    'progress' => array('type' => 'hidden'),
    // url to be called in ajax
    'path' => 'system/ajax/rue89/user/register'
  ),
);
```

  