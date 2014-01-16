http://www.addedbytes.com/articles/for-beginners/url-rewriting-for-beginners    

Default Drupal rewrite conditions
````
 # Rewrite URLs of the form 'x' to the form 'index.php?q=x'.
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteCond %{REQUEST_URI} !=/favicon.ico
  RewriteRule ^(.*)$ index.php?q=$1 [L,QSA]
````


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
````
RewriteEngine On    # Turn on the rewriting engine
RewriteRule    ^pet-care/?$    pet_care_info_01_02_2008.php    [NC,L] 
````
http://www.addedbytes.com/articles/for-beginners/url-rewriting-for-beginners/ > 
>  
The "RewriteRule" line is where the magic happens. The line can be broken down into 5 parts:

RewriteRule - Tells Apache that this like refers to a single RewriteRule.
^/pet-care/?$ - The "pattern". The server will check the URL of every request to the site to see if this pattern matches. If it does, then Apache will swap the URL of the request for the "substitution" section that follows.
pet_care_info_01_02_2003.php - The "substitution". If the pattern above matches the request, Apache uses this URL instead of the requested URL.
[NC,L] - "Flags", that tell Apache how to apply the rule. In this case, we're using two flags. "NC", tells Apache that this rule should be case-insensitive, and "L" tells Apache not to process any more rules if this one is used.
# Handle requests for "pet-care" - Comment explaining what the rule does (optional but recommended)
> 