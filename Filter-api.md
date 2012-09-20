### API 

* **hook_filter_info**   
http://api.drupal.org/api/drupal/modules!filter!filter.api.php/function/hook_filter_info/7   
Define the new input filter. 
We should define the callback function used in this filter which are several 
```
'prepare callback' => '_filter_example_filter_time_prepare',
'process callback' => '_filter_example_filter_time_process',
'tips callback' => '_filter_example_filter_time_tips',
```
Example asset module https://gist.github.com/1cc86c91caf877f2d43b   
Example example module https://gist.github.com/8717b18592c45d4cd1f8

* **_text_sanitize**   
http://api.drupal.org/api/drupal/modules%21field%21modules%21text%21text.module/function/_text_sanitize/7   
Transform value in safe value in the form api for example

* **valid_email_adress**   
http://api.drupal.org/api/drupal/includes!common.inc/function/valid_email_address/7
Validate that an email adress is a true one 

### HOOKS