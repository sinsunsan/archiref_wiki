* **Install drush with git**   
http://drupal.org/project/drush/git-instructions
```git clone --recursive --branch master http://git.drupal.org/project/drush.git```


* **drush php-eval**
Allow to evaluate php code after drupal bootstrap   

Which directory is returned by the bootstrap function conf_path   
````
drush php-eval "print(conf_path());"
````

* **drush sa**   
List all site aliases defined