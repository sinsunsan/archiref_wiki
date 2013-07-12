https://api.drupal.org/api/drupal/includes!entity.inc/class/EntityFieldQuery/7

Exemple :
````
	$entities = $query->entityCondition('entity_type', 'node')
	->propertyCondition('type', array('territoire_departement','territoires_r_gion'),'IN')
	->propertyCondition('title', strtolower(arg(2)))
	->range(0,1)
	->execute();

````
