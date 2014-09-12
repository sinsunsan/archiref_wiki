### My module is not defined ?

a module can't be created with 
```js
angular.module('mysite.calendar.directives')
```

even if you don't have dependencies you need to write 
```js
angular.module('mysite.calendar.directives', [])
```

### A directive is not interpreted. 

Generally there is a dependency with per aps the directives module. 
It don't throw an error. But a way to quick debug is to copy the directives code, assign it to the module of the current controller.

### Argument 'myCtrl' is not a function, got undefined    
> 
Argument 'TeamCtrl' is not a function, got undefined    
http://errors.angularjs.org/1.3.0-beta.2/ng/areq?p0=TeamCtrl&p1=not%20a%20function%2C%20got%20undefined

This error, when angular faile to inject the controller. 
There is 2 ways to set the controller to a portion of code : 
* by setting ng-controller="myCtrl" in the html 
* with $route definition 

By removing these references, we remove the error, but our controller is not yet loaded !

***
### TYPO Problem with coma    
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
***
### Unwanted redefinition of the module      

http://stackoverflow.com/questions/19719540/angularjs-jade-error-argument-mycontroller-is-not-a-function-got-undefined
  
This error mostly comes when angularjs is not able to locate the controller in any module. This can happen when you accidentally redefine the module. In your case i see that
````
window.app = angular.module('mean', ['ngCookies', 'ngResource', 'ui.bootstrap', 'ui.route', 'mean.system', 'mean.articles' ]);
````
and then

```` var mean = angular.module('mean',[]);````

This syntax redefine the module.

To get the existing module using angular.module('mean') without the second parameter.

*** 

### [[angular memory leaks]]

* Unbinding jquery event listening
http://stackoverflow.com/questions/22397484/how-to-reduce-remove-memory-leaks-in-angular-application

***
### Template for directive 'minisearch' must have exactly one root element.

Template for directive 'minisearch' must have exactly one root element. template/minisearch.html

Was 
````js
<!-- Mini search bar integrated to the header-->
<div class="search-mini">
  <form action="/images#!/images" method="GET" ng-submit="goTo()">
    <div class="input-group">
      <input type="text" placeholder="Search images..." ng-show="searchMini" class="form-control"><span ng-click="searchMini = !searchMini" class="input-group-addon"><i class="fa fa-search"></i></span>
    </div>
  </form>
</div>
````
And the <!-- Mini search bar integrated to the header-->
Was considered as a html element ! so either remove the comment either wrap it inside <div class="search-mini">
