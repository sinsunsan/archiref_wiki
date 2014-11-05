### Liste of Angular recipes     
* https://leanpub.com/recipes-with-angular-js/read
* http://fdietz.github.io/recipes-with-angular-js/toc.html
* http://fdietz.github.io/recipes-with-angular-js/common-user-interface-patterns/

#### My Recipes

* **Print a class name depending of the value of a variable**   
http://stackoverflow.com/questions/14735257/what-angularjs-expression-syntax-is-this-in-ng-class

* **Click to edit a field**   
http://icelab.com.au/articles/click-to-edit-with-angularjs/   
http://icelab.com.au/articles/levelling-up-with-angularjs-building-a-reusable-click-to-edit-directive/

* **Change the url without reloading the page**   
http://stackoverflow.com/questions/18337093/updating-url-in-angular-js-without-re-rendering-view   
But have the page reloaded for specific cases   
http://stackoverflow.com/questions/19137504/force-angularjs-to-reload-a-route-although-option-reloadonsearch-is-set-to-false

* **Change the display only when the services have returned their data to prevent the flicker effect**   
http://stackoverflow.com/questions/11972026/delaying-angularjs-route-change-until-model-loaded-to-prevent-flicker?rq=1

* **Combine different app / module in the same page**   
http://stackoverflow.com/questions/12860595/how-to-define-two-angular-apps-modules-in-one-page   
http://www.simplygoodcode.com/2014/04/angularjs-getting-around-ngapp-limitations-with-ngmodule

* **Toogling the visibility of an element**    
http://geniuscarrier.com/ng-toggle-in-angularjs/
http://jsfiddle.net/geniuscarrier/tKZjZ/55/

* **Angular hash route and real hash**   
````
http://localhost:18080/equipe#!/#blocHistory
````
In this url #! is the hash + bang used by angular, the path is / and the real plain hash is #blocHistory

* **Object and object properties** 

Example of handling of all properties and some properties of an object 
**search.$** @todo learn more about
````js
Any: <input ng-model="search.$"> <br>
Name only <input ng-model="search.name"><br>
Phone only <input ng-model="search.phone"><br>
````
https://docs.angularjs.org/api/ng/filter/filter

* **Filter results for non null value of a field** 
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

* **Call a controller function everywhere in the code (not only from a controller...)**      
http://stackoverflow.com/questions/16709373/angularjs-how-to-call-controller-function-from-outside-of-controller-component


***

* **Communicate between controller** 

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
* **Hide an element before ng-show ng-hide has taken controll** 

You can use the same ng-hide ng-show classes that are used by ng-show, ng-hide directives. 
This way, when the value that is evaluated by ng-hide will be used, it will remove or leave the class manually set in the template.

<div class="ng-hide" ng-hide="myValue" >

* if $scope.myValue = true, the ng-hide class is left
* if $scope.myValue = false, the ng-hide class is removed