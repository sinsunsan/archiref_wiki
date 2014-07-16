### General facts about scopes

https://github.com/angular/angular.js/wiki/Understanding-Scopes

* ng-repeat, ng-view and ng-switch create a scope 
* scope are prototypally inherited from their parent scope

http://stackoverflow.com/questions/14049480/what-are-the-nuances-of-scope-prototypal-prototypical-inheritance-in-angularjs

### How to comunicate between scope 
* Propagate a child scope variable to parent scope    
http://stackoverflow.com/questions/16972976/angular-js-propagate-child-scope-variable-changes-to-parent-scope#

http://stackoverflow.com/questions/14502006/scope-emit-and-on-angularjs

> First of all, parent-child scope relation does matter. You have two possibilities to emit some event:

> $broadcast -- dispatches the event downwards to all child scopes,
> $emit -- dispatches the event upwards through the scope hierarchy.
> I don't know anything about your controllers (scopes) relation, but there are several options:

> If scope of firstCtrl is parent of the secondCtrl scope, your code should work by replacing $emit by $broadcast in firstCtrl:

> function firstCtrl($scope){
>     $scope.$broadcast('someEvent', [1,2,3]);
> }

> function secondCtrl($scope){
>     $scope.$on('someEvent', function(event, mass) {console.log(mass)});
> }
> In case there is no parent-child relation between your scopes you can inject $rootScope into the controller and broadcast the event to all child scopes (i.e. also secondCtrl).

> function firstCtrl($rootScope){
>     $rootScope.$broadcast('someEvent', [1,2,3]);
> }
> Finally, when you need to dispatch the event from child controller to scopes upwards you can use $scope.$emit. If scope of firstCtrl is parent of the secondCtrl scope:

> function firstCtrl($scope){
>     $scope.$on('someEvent', function(event, data) { console.log(data); });
> }

> function secondCtrl($scope){
>     $scope.$emit('someEvent', [1,2,3]);
> }