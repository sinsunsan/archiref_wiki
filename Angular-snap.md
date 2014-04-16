### How to redefined the options 

https://github.com/jtrussell/angular-snap.js

> In the config as explained 
> Options

> You can pass initialization parameters to the Snap constructor :

> angular.module('myApp', ['snap'])
>   .config(function(snapRemoteProvider) {
>     snapRemoteProvider.globalOptions.disable = 'right';
>     // or
>     snapRemoteProvider.globalOptions = {
>       disable: 'right',
>       // ... others options
>     }
>   })
> You can also use the snap-options attribute on the same element with the snap-contents directive.

> In your controller:

> $scope.opts = {
>   disable: 'right'
> };
> In your view:

> <snap-content snap-options="opts">...</snap-content>
> The snap-content directive will watch your snap-options object for runtime changes and update itself as you make them.

The options are redefined in the controller   
https://github.com/jtrussell/angular-snap.js/blob/master/examples/js/controllers.js
````
.controller('ExOptionsCtrl', function($scope) {
    'use strict';
    $scope.snapOpts = {
      disable: 'none'
    };

    $scope.disable = function(side) {
      $scope.snapOpts.disable = side;
    };

    $scope.enable = function() {
      $scope.snapOpts.disable = 'none';
    };
  })
````

And the name of the snapOpts is defined in this directive    
https://github.com/jtrussell/angular-snap.js/blob/master/examples/partials/ex-options.html
````  
<snap-content snap-options="snapOpts">
```` 