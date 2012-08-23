Since Drupal 7, it's possible to create a table with checkobox and action like in VBO, but as a form. 

A new key exist #tableselect make the link element a table.     
http://heine.familiedeelstra.com/book/export/html/1430   
http://api.drupal.org/api/drupal/developer!topics!forms_api_reference.html/7#tableselect    


``` php
<?php
/**
 * Menu callback: Display the suggestion management form.
 *
 * @return $form
 */
function rue89_unitag_manage_suggestions_form($form, &$form_state) {
  $form['controls'] = array(
    '#type' => 'fieldset',
    '#title' => t('Update options'),
    '#description' => t('Approve or deny the selected suggestions. These operations will only work with vocabularies that support them.'),
  );
  $form['controls']['operation'] = array(
    '#type' => 'select',
    '#options' => array(
      'new-term' => t('Approve as new terms'),
      'deny' => t('Deny and delete'),
    ),
    '#prefix' => '<div class="container-inline">',
  );

  $form['controls']['submit'] = array(
    '#type' => 'submit',
    '#value' => t('Update'),
    '#suffix' => '</div>',
  );
  
  // Grab available suggestions.
  $suggestions = rue89_unitag_suggestions_get();
  $utids = array();
  foreach ($suggestions as $suggestion) {
    $vocabulary = taxonomy_vocabulary_load($suggestion->vid);
    $node = node_load($suggestion->nid);
    $utids[$suggestion->utid] = array(
      'name' => array('data' => $suggestion->name),
      'node' => array('data' => array(
        '#type' => 'link',
        '#title' => check_plain($node->title),
        '#href' => 'node/' . $suggestion->nid,
        '#suffix' => ' (nid:' . $suggestion->nid . ')',
      )),
      'vocabulary' => array('data' => array(
        '#type' => 'link',
        '#title' => check_plain($vocabulary->name),
        '#href' => 'admin/structure/taxonomy/' . $vocabulary->machine_name,
        '#suffix' => '(fid:' . $suggestion->field . ')',
      )),
      'operations' => array('data' => l(t('Edit'), 'admin/structure/unitag/manage/' . $suggestion->utid . '/edit')),
    );
  }
  
  $header = array(
    'name' => array('data' => t('Name')),
    'node' => array('data' => t('Node')),
    'vocabulary' => array('data' => t('Vocabulary')),
    'operations' => array('data' => t('Operations')),
  );
  
  $form['utids'] = array(
    '#type' => 'tableselect',
    '#header' => $header,
    '#options' => $utids,
    '#empty' => t('No content available.'),
  );

  return $form;
}
?>
```
