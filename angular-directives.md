### Selection of [[angular directives libraries]]
### Writing a custom directives

* http://www.ng-newsletter.com/posts/directives.html
* https://docs.angularjs.org/guide/directive
* http://www.sitepoint.com/practical-guide-angularjs-directives/
* https://github.com/angular/angular.js/wiki/Understanding-Scopes#directives
* Exemple of a carefully coded directive       
https://github.com/Venturocket/angular-slider/blob/master/src/angular-slider.js
* Good alternatives guides to directives      
 http://amitgharat.wordpress.com/2013/06/08/the-hitchhikers-guide-to-the-directive/

* how to call the directive in the html 
If the directive was created like this 
````
angular.module('snap')
    .directive('snapCloseOnResize', ['$rootscope', 'snapRemote', function($rootScope, snapRemote) {
        return {
                restrict: 'A',
                link: function (scope, element, attrs) {
                }
            };
    }]);
````
To use is we need to name an attribute with the name of the directive.    
The name with camel Case need the be slighly changed to use -    
snapCloseOnResize  > snap-close-on-resize    
And as restrict is set to A.    
It must be an attribute 
So we call the directives with 
````
<div snap-close-on-resize class="my-div>
</div>
 
````


### Directive options 

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

Fiddle that show the difference between the 3 bindings    
http://jsfiddle.net/maxisam/QrCXh/

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

### In which order the directives are compiled

https://groups.google.com/forum/#!topic/angular/3HsNz4ncnYA/discussion
http://plnkr.co/edit/qrDMJBlnwdNlfBqEEXL2?p=preview

> The compilation works depth first down.  So html->alpha->beta->gamma
But the post link functions come back up So gamma->beta->alpha-html
Moreover if you have multiple directives on an element, they are compiled in order of their priority value, highest first, with directives of the same priority having undetermined order.

### Link function 
Simple directive that take the href attributes of the element the directive is on and scroll to the anchor. 
HTML
```` html
<a scroll-on-click="" href="#blocTeam">The team</a>
````
DIRECTIVE
```` js
app.directive( 'scrollOnClick', function() {
    return {
        restrict: 'A',
        link: function(scope, $elm, attrs) {
            console.log('scroll activé');
            var idToScroll = attrs.href;
            $elm.on('click', function() {
                var $target;
                if (idToScroll) {
                    $target = $(idToScroll);
                } else {
                    $target = $elm;
                }
                $("body,html").animate({scrollTop: $target.offset().top - 30}, "slow");

                // bug fix for a flash with webkit
                return false;
            });
        }
    }
});
````
### Standard directives 

* **[[ngClass]]**     

