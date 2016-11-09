* http://www.undefinednull.com/2014/02/11/mastering-the-scope-of-a-directive-in-angularjs/
* https://umur.io/angularjs-directives-using-isolated-scope-with-attributes/
* http://onehungrymind.com/angularjs-sticky-notes-pt-2-isolated-scope/

### Passing a function from the parent controller to the directive scope 

* http://jsfiddle.net/yMHe4/

### Directive options 
### How to choose between the 3 scope options 

* No scope 
* Child Scope 
* Isolated scope 

http://stackoverflow.com/questions/14914213/when-writing-a-directive-how-do-i-decide-if-a-need-no-new-scope-a-new-child-sc


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
// In the html attribute color="color" need to be a model 

````
To have a one way data binding (when the parent changed, the directive variable change, but not in the other way 
````
scope: {
        customerInfo: '@'
      },
// In the html attribute  name="{{name}}"
Needn to be an expression wrapped in {{}}

````
Method binding &
// In the html attribute reverse="reverseName()"

#### How to use @ operator and function in the context of the parent scope 

* http://stackoverflow.com/questions/23477859/angularjs-call-function-on-directive-parent-scope-with-directive-scope-argumen

* Version using = operator :
 http://plnkr.co/edit/9fusO7XsunFkpXxXkgIJ?p=preview

* Version using & operator :
 http://plnkr.co/edit/kzPRxAdG24Y7k0xFanZP?p=preview

#### Exemples


Fiddle that show the difference between the 3 bindings    
http://jsfiddle.net/maxisam/QrCXh/
http://stackoverflow.com/questions/17900201/how-to-access-parent-scope-from-within-a-custom-directive-with-own-scope-in-an

* Tips : it's possible to know which type of binding the directive has by reading the class applyied to the directive element "ng-isolate-scope" for example