
Allow to quickly toogle a set of variable by replacing 1 == 0 by 1 == 1

```
if (1 == 0) {
  $conf['cache'] = '0';
  $conf['block_cache'] = '0';
  $conf['cache_backends'][] = 'includes/cache-install.inc';
  $conf['cache_default_class'] = 'DrupalFakeCache';
  $conf['page_cache_without_database'] = TRUE;
  $conf['page_cache_invoke_hooks'] = FALSE;
  $conf['cache_class_cache_form'] = 'DrupalDatabaseCache';
}
```
