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
<?php
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

### What's going on during the batch   
```
<?php 
/**
 * Batch # rue89_qr_batch_qr_update_statuses : 
 */
function rue89_qr_batch_qr_update_statuses_process(&$context) {
  if (empty($context['sandbox'])) {
    $context['sandbox']['progress'] = 0;
    $context['sandbox']['current_node'] = 0;
    $context['sandbox']['max'] = db_query('SELECT COUNT(n.nid) FROM {node} n WHERE n.type = :type', array(':type' => 'q_r'))->fetchField();
    $context['message'] = t('Total QR nodes detected: @count.', array('@count' => $context['sandbox']['max']));
  }

  $result = db_query('SELECT n.nid FROM {node} n WHERE n.nid > :nid AND n.type = :type ORDER BY n.nid ASC LIMIT 0,5', array(':nid' => $context['sandbox']['current_node'], ':type' => 'q_r'))->fetchCol();
  module_load_include('inc', 'rue89_qr', 'includes/rue89_qr.drush');

  foreach ($result as $nid) {
    $node = node_load($nid);
    $node->field_qr_status[LANGUAGE_NONE] = array(array('value' => 3));
    $node->field_mobile_display[LANGUAGE_NONE] = array(array('value' => 'web'));
    rue89_qr_update_questions($node);

    $context['sandbox']['progress']++;
    $context['sandbox']['current_node'] = $nid;
  }

  if ($context['sandbox']['progress'] != $context['sandbox']['max']) {
    $context['finished'] = $context['sandbox']['progress'] / $context['sandbox']['max'];
  }
  $context['message'] = t('Progress: @progress% (@current of @max)', array('@progress' => round($context['finished'] * 100), '@current' => $context['sandbox']['progress'], '@max' => $context['sandbox']['max']));
}
```