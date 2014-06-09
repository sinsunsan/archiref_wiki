> 
Argument 'TeamCtrl' is not a function, got undefined    
http://errors.angularjs.org/1.3.0-beta.2/ng/areq?p0=TeamCtrl&p1=not%20a%20function%2C%20got%20undefined

* http://stackoverflow.com/questions/21061773/angular-error-argument-controller-is-not-a-function-got-undefined
Typo problem 
```` js
// Good
angcomControllers.controller('itemsController', ['$scope', 'Items', function($scope, Items){
}]);
// Bad
angcomControllers.controller('itemsController' ['$scope', 'Items', function($scope, Items){
}]);
````