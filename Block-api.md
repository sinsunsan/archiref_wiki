In d6 there was only hook_block with different op 

In d7, there is a hook by operation like 
* **hook_block_view**   
https://api.drupal.org/api/drupal/modules!block!block.api.php/function/hook_block_view/7       
Define how to display a block   

* **hook_block_info**   
https://api.drupal.org/api/drupal/modules!block!block.api.php/function/hook_block_info/7   
Define news blocks
Definition of new block 
```
function mymodule_block_info() {
    $blocks['block1'] = array(
        'info' => t('My new block'),
        'cache' => DRUPAL_CACHE_PER_PAGE,
        'region' => 'sidebar_first',
        'status' => 1,
    );
    return $blocks;
}
```