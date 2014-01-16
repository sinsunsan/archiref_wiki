Default Drupal rewrite conditions
````
 # Rewrite URLs of the form 'x' to the form 'index.php?q=x'.
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_URI} !=/favicon.ico
  RewriteRule ^(.*)$ index.php?q=$1 [L,QSA]
````

* Redirecting only a folder    
http://coolestguidesontheplanet.com/redirecting-a-web-folder-directory-to-another-in-htaccess   
