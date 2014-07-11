https://docs.angularjs.org/guide/filter

## How to use filters 

It's possible to use a filter in an expression like in a ng-repeat 
or in the js code like 
````js
var orderBy = $filter('orderBy');
$scope.friends = orderBy($scope.friends, predicate, reverse);
````
## Built in filters 
### Date   
Format a date for display   
https://docs.angularjs.org/api/ng/filter/date

### Order By    
Allow to reorder a list with ng-repeat...    
https://docs.angularjs.org/api/ng/filter/orderBy

### Filter (the filter filter...)
Return a sub array of the given array (generally in the context of ng-repeat)
https://docs.angularjs.org/api/ng/filter/filter
