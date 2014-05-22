### Writing a custom directives

* https://docs.angularjs.org/guide/directive
* http://www.sitepoint.com/practical-guide-angularjs-directives/
* https://github.com/angular/angular.js/wiki/Understanding-Scopes#directives

### Directive options 

* **scope**    
= mean customerInfo inner scope variable       
will be bound to info parent scope variable 
in a 2 ways data bindings. It mean if customerInfo is changed
info is also changed
````
scope: {
        customerInfo: '=info'
      },
````

### Best pratices to create directive

http://www.sitepoint.com/practical-guide-angularjs-directives/

* In order to avoid collisions with some future standard, it's best to prefix your own directive names.
* Unless your template is very small, it's typically better to break it apart into its own HTML file and load it with the templateUrl option.
* **When should I use an attribute versus an element** ? Use an element when you are creating a component that is in control of the template. Use an attribute when you are decorating an existing element with new functionality.
* Use the scope option to create isolate scopes when making components that you want to reuse throughout your app.

### Create an isolate scope in a directive
Angular js files
````js
angular.module('docsIsolateScopeDirective', [])
  .controller('Controller', ['$scope', function($scope) {
    $scope.naomi = { name: 'Naomi', address: '1600 Amphitheatre' };
    $scope.igor = { name: 'Igor', address: '123 Somewhere' };
  }])
  .directive('myCustomer', function() {
    return {
      restrict: 'E',
      scope: {
        customerInfo: '=info'
      },
      templateUrl: 'my-customer-iso.html'
    };
  });
````
Html
````html
<div ng-controller="Controller">
  <my-customer info="naomi"></my-customer>
  <hr>
  <my-customer info="igor"></my-customer>
</div>
````
Directive template
````html 
Name: {{customerInfo.name}} Address: {{customerInfo.address}}
````
> Note: Normally, a scope prototypically inherits from its parent. An isolated scope does not. See the "Directive Definition Object - scope" section for more information about isolate scopes.


### Standard directives 

* **[[ngClass]]**     


### Contributed directives 

* Timer, countdown...    
http://siddii.github.io/angular-timer/index.html