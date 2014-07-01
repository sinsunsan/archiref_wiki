### Directive options 

#### Important notice about how to understand directives binding

$scope.customerInfo inner directive variable will be binded to parent scope $scope.info. 
We say that 
$scope.customerInfo inner directive variable will be binded to what we passed to it in the directive definition

<myelement info="myparentInfo" > Will actually bind inner $scope.customerInfo to outer $scope.myparentInfo via the attribue info

#### Type of bindings

* **scope** 
  * false (default) no inheritance, the parent scope and directive scope is the same 
  * true protypal inheritance like ng-include 
  * scope : {} Define a innner scope isolated from external scope 
 **customerInfo: '=info'** mean customerInfo inner scope variable       
will be bound to info parent scope variable 
in a 2 ways data bindings. It mean is changed in the directive
customerInfo will be also changed

````
scope: {
        customerInfo: '=info'
      },
````
If the name of the variable in the inner scope or outer scope is the same, we can use the shortcut
````
scope: {
        customerInfo: '='
      },
````
To have a one way data binding (when the parent changed, the directive variable change, but not in the other way 
````
scope: {
        customerInfo: '@'
      },
````

#### Exemples


Fiddle that show the difference between the 3 bindings    
http://jsfiddle.net/maxisam/QrCXh/
http://stackoverflow.com/questions/17900201/how-to-access-parent-scope-from-within-a-custom-directive-with-own-scope-in-an

* Tips : it's possible to know which type of binding the directive has by reading the class applyied to the directive element "ng-isolate-scope" for example