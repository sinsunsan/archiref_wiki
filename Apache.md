* **securing an apache directory with a password**   

http://www.addedbytes.com/blog/code/password-protect-a-directory-with-htaccess/


* **Redirection**
We can user mod_alias or mod_rewrite 
mod_alias is easier 
http://httpd.apache.org/docs/current/mod/mod_alias.html

To redirect all pages of a site to the home page of another site
```
Options +FollowSymLinks
RewriteEngine on
RedirectMatch (.*)$ http://www.thalweg.fr
```
If using redirect directive the path is preserved, but in this case, we wanted all requests to old domain to be done to the other domain