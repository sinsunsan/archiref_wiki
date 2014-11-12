### Best pratices documents 
* https://google-styleguide.googlecode.com/svn/trunk/angularjs-google-style.html#moduledeps    
Git commit for angular best practice
* https://github.com/jmcunningham/angularjs-styleguide Complete opiniated angular guide
* https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#

### General Pitfalls

* http://nathanleclaire.com/blog/2014/04/19/5-angularjs-antipatterns-and-pitfalls/

### Scope Pitfalls 

* http://thenittygritty.co/angularjs-pitfalls-using-scopes
* http://www.technofattie.com/2014/03/21/five-guidelines-for-avoiding-scope-soup-in-angular.html

### Share code between controller / "the controller as" syntax 
* TO READ ON HOW TO BETTER USE ANGULAR JS controller    
http://toddmotto.com/rethinking-angular-js-controllers/
http://toddmotto.com/digging-into-angulars-controller-as-syntax/

Rules for the Controller going forward:

* Controllers should hold zero logic
* Controllers should bind references to Models only (and call methods returned from promises)
* Controllers only bring logic together
* Controller drives Model changes, and View changes. Keyword; drives, not creates/persists, it triggers them!
* Delegate updating of logic inside Factories, don't resolve data inside a Controller, only update the Controller's value with updated Factory logic, this avoids repeated code across Controllers as well as Factory tests made easier
* Use "Controller as" (read the article)
* Keep things simple, I prefer XXXXCtrl and XXXXFactory, I know exactly what the two do, we don't need fancy names for things
* Keep method/prop names consistent across shared methods, such as this.something = MyFactory.something; otherwise it becomes confusing
* Factories hold the Model, change, get, update, and persist the Model changes
* Think about the Factory as an Object that you need to persist, rather than persisting inside a Controller
* Talk to other Factories inside your Factory, keep them out the Controller (things like success/error handling)
* Try to avoid injecting $scope into Controllers, generally there are better ways to do what you need, such as avoiding $scope.$watch()

### Minification syntax 

For dependency injection, it's a good pratice to use the array `[$scope, $log, function($scope, $log` syntax

http://stackoverflow.com/questions/16055449/angularjs-minification-issue-in-directive

### this vs scope 
* http://odetocode.com/blogs/scott/archive/2014/08/11/thoughts-on-angular-controller-as-syntax.aspx
* http://stackoverflow.com/questions/11605917/this-vs-scope-in-angularjs-controllers/14168699#14168699

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