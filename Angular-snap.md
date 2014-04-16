
### How to redefined the options 


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