* http://thenittygritty.co/angularjs-pitfalls-using-scopes
* http://www.technofattie.com/2014/03/21/five-guidelines-for-avoiding-scope-soup-in-angular.html


### Modularization 

#### Module definition 

http://henriquat.re/modularizing-angularjs/modularizing-angular-applications/modularizing-angular-applications.html
Pollute global variable space
```` js
var mod = angular.module("foo", []);
mod.directive("directiveA", function() { /* ... */ });
mod.directive("directiveB", function() { /* ... */ });
mod.directive("directiveC", function() { /* ... */ });
````
chainable structure don't pollute global space
```` js
angular.module("foo", [])
   .directive("directiveA", function() { /* ... */ })
   .directive("directiveB", function() { /* ... */ })
   .directive("directiveC", function() { /* ... */ });
````

If the definition of the module need to be updated in other file 
```` js
angular.module("name").directive...
````
Without redefining the depency array 

#### module splitting 

Split module by functionallity rather than by type (inbox, composer....) rather than (services, controllers....)
