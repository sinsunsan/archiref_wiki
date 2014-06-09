> 
Argument 'TeamCtrl' is not a function, got undefined    
http://errors.angularjs.org/1.3.0-beta.2/ng/areq?p0=TeamCtrl&p1=not%20a%20function%2C%20got%20undefined

* TYPO Problem with coma    
http://stackoverflow.com/questions/21061773/angular-error-argument-controller-is-not-a-function-got-undefined    
Typo problem 
```` js
// Good
angcomControllers.controller('itemsController', ['$scope', 'Items', function($scope, Items){
}]);
// Bad
angcomControllers.controller('itemsController' ['$scope', 'Items', function($scope, Items){
}]);
````

* Unwanted redefinition of the module      

http://stackoverflow.com/questions/19719540/angularjs-jade-error-argument-mycontroller-is-not-a-function-got-undefined
  
This error mostly comes when angularjs is not able to locate the controller in any module. This can happen when you accidentally redefine the module. In your case i see that
````
window.app = angular.module('mean', ['ngCookies', 'ngResource', 'ui.bootstrap', 'ui.route', 'mean.system', 'mean.articles' ]);
````
and then

```` var mean = angular.module('mean',[]);````

This syntax redefine the module.

To get the existing module using angular.module('mean') without the second parameter.