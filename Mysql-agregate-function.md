Group by function that list all node by type in a drupal site
````
SELECT COUNT(type), type from node GROUP BY type ORDER BY count(type) DESC
````