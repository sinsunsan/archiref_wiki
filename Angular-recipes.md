## Liste of Angular recipes     
* https://leanpub.com/recipes-with-angular-js/read
* http://fdietz.github.io/recipes-with-angular-js/toc.html
* http://fdietz.github.io/recipes-with-angular-js/common-user-interface-patterns/

## My Recipes

### **Print a class name depending of the value of a variable**   
http://stackoverflow.com/questions/14735257/what-angularjs-expression-syntax-is-this-in-ng-class

### **Click to edit a field**   
http://icelab.com.au/articles/click-to-edit-with-angularjs/   
http://icelab.com.au/articles/levelling-up-with-angularjs-building-a-reusable-click-to-edit-directive/

### **Change the url without reloading the page**   
http://stackoverflow.com/questions/18337093/updating-url-in-angular-js-without-re-rendering-view   
But have the page reloaded for specific cases   
http://stackoverflow.com/questions/19137504/force-angularjs-to-reload-a-route-although-option-reloadonsearch-is-set-to-false

### **Change the display only when the services have returned their data to prevent the flicker effect**   
http://stackoverflow.com/questions/11972026/delaying-angularjs-route-change-until-model-loaded-to-prevent-flicker?rq=1

* put ng-hide on the element to hide 
* don't user fonction to deal with hidden state as it takes more time to evaluate at the drawing startup 
* use simple condition 

ng-cloak is for preventing to see {{var}} not to deal with hide issue 

* another alternative could be to set a timer thanks to the router, but it is the ui-router part of the view that can be handled this way 

### **Combine different app / module in the same page**   
http://stackoverflow.com/questions/12860595/how-to-define-two-angular-apps-modules-in-one-page   
http://www.simplygoodcode.com/2014/04/angularjs-getting-around-ngapp-limitations-with-ngmodule

### **Toogling the visibility of an element**    
http://geniuscarrier.com/ng-toggle-in-angularjs/
http://jsfiddle.net/geniuscarrier/tKZjZ/55/

### **Angular hash route and real hash**   
````
http://localhost:18080/equipe#!/#blocHistory
````
In this url #! is the hash + bang used by angular, the path is / and the real plain hash is #blocHistory

### **Object and object properties** 

Example of handling of all properties and some properties of an object 
**search.$** @todo learn more about
````js
Any: <input ng-model="search.$"> <br>
Name only <input ng-model="search.name"><br>
Phone only <input ng-model="search.phone"><br>
````
https://docs.angularjs.org/api/ng/filter/filter

### **Filter results for non null value of a field** 
To filter for result that have null field you can do 
````
ng-repeat="aliment in dated.aliments | filter: {ingredient_id: null}"
````
But how to do for non null field ?
There is a small syntax for that
````
ng-repeat="aliment in dated.aliments | filter: {ingredient_id: '!!'}"
````

http://jsfiddle.net/TheSharpieOne/RGEdc/

### **Call a controller function everywhere in the code (not only from a controller...)**      
http://stackoverflow.com/questions/16709373/angularjs-how-to-call-controller-function-from-outside-of-controller-component


***

### **Communicate between controller** 

http://stackoverflow.com/questions/9293423/can-one-controller-call-another-in-angularjs#

here are multiple ways how to communicate between controllers.

The best one is probably sharing a service:

function FirstController(someDataService) {
  // use the data service, bind to template...
  // or call methods on someDataService to send a request to server
}

function SecondController(someDataService) {
  // has a reference to the same instance of the service
  // so if the service updates state for example, this controller knows about it
}
Another way is emitting an event on scope:
````js
function FirstController($scope) {
  $scope.$on('someEvent', function(event, args) {});
  // another controller or even directive
}

function SecondController($scope) {
  $scope.$emit('someEvent', args);
}
````
In both cases, you can communicate with any directive as well...
https://www.youtube.com/watch?v=1OALSkJGsRw

***
### **Get the old and new value with ng-change**
http://stackoverflow.com/questions/26621104/ng-change-get-new-value-and-original-value

***
### **Hide an element before ng-show ng-hide has taken controll** 

You can use the same ng-hide ng-show classes that are used by ng-show, ng-hide directives. 
This way, when the value that is evaluated by ng-hide will be used, it will remove or leave the class manually set in the template.

<div class="ng-hide" ng-hide="myValue" >

* if $scope.myValue = true, the ng-hide class is left
* if $scope.myValue = false, the ng-hide class is removed

***
### **use controller inheritance with controller as syntax** 

http://stackoverflow.com/questions/26351163/how-to-inherit-from-base-controller-using-controller-as-syntax

### Combine promises 

What if we want to resolve when all promises have been resolved ? 

https://www.jonathanfielding.com/combining-promises-angular/

### List the content of a angular module 

````
angular.module('moduleNAme')._invokeQueue
````
TO search in this array, here is a snippet
Ok for constants, values, factories, services. (but not directives)

````
function allServices(mod, r) {
      var inj = angular.element(document).injector().get;
      if (!r) r = {};
      angular.forEach(angular.module(mod).requires, function(m) {allServices(m,r)});
      angular.forEach(angular.module(mod)._invokeQueue, function(a) {
        try { r[a[2][0]] = inj(a[2][0]); } catch (e) {}
      });
      return r;
    };

    allMyServices = allServices('myApp');
````

### Focus give the focus to a field

* http://stackoverflow.com/questions/25596399/set-element-focus-in-angular-way
* https://github.com/angular-ui/ui-select/issues/100
* https://www.emberex.com/programmatically-setting-focus-angularjs-way/


### Prevent duplicate call with $rootScope.$on

When navigating away from a page, the old listeners do not get destroyed with the page scope. So a duplicate call of $rootScope can end up by calling api requests many times (the more we have navigated in the site, the many requests are made). Of course we can use a bolean with a timer to prevent multiple calls, but it is not a clean way to do it. 


Instead use the recipe described here
``` js
var destroyFoo;

destroyFoo = $rootScope.$on('foo', function() {});

$scope.$on('$destroy', function() {
  destroyFoo(); // remove listener.
});  
```
* http://stackoverflow.com/questions/19553598/angularjs-broadcast-repeating-execution-too-many-times