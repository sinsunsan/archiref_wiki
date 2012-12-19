http://api.drupal.org/api/drupal/includes%21form.inc/group/batch/7

Example of settings a batch to update a type of node 
``` php
<?php 
/**
 * Implements hook_menu().
 */
function rue89_qr_menu() {
  $items = array();
  $items['admin/news/batch/qr-update-statuses'] = array(
    'title' => 'Update QR statuses',
    'type' => MENU_CALLBACK,
    'page callback' => 'rue89_qr_batch_qr_update_statuses',
    'page arguments' => array(),
    'access arguments' => array('administer site configuration'),
  );
}
```