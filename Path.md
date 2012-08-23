http://stackoverflow.com/questions/703426/how-to-get-the-full-url-of-a-drupal-page


### To return the full url with ? and aliased path 

<pre>
global $base_root;
$vars['feed_url'] = $base_root . request_uri();
</pre>

