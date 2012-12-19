Example of settings a batch to update a type of node 

### Hook Menu to define the page where the batch are going to take place
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

### Batch definition and call

```
/**
 * Batch # rue89_qr_batch_qr_update_statuses : 
 */
function rue89_qr_batch_qr_update_statuses() {
  $batch = array(
    'title' => t('Update QR statuses'),
    'operations' => array(
      array('rue89_qr_batch_qr_update_statuses_process', array()),
    ),
    'finished' => 'rue89_qr_batch_qr_update_statuses_finished',
  );
  batch_set($batch);
  batch_process(NULL);
}
```
