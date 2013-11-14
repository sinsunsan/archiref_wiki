* set config in a [[.htaccess]] file

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
If using redirect directive the path is preserved, but in this case, we wanted all requests to old domain to be done to the other domain. 
It's not the cleaner method, as google couldn't identify each old page / new page association. 
Would be preferible that all path where mapped to all domain, but don't know how to remove the dir part of the domain
5.9.82.45/dev/thalweg/www/