* https://github.com/olov/ng-annotate 
automatically annotatate dependency injection, no more need to do it by hand.    
````
angular.module("MyMod").controller("MyCtrl", ["$scope", "$timeout", function($scope, $timeout) {
````
Exemple config
http://bguiz.github.io/js-standards/angularjs/minification-and-annotation/