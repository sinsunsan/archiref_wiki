



The options are redefined in the controller
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
```` 
<snap-content snap-options="snapOpts">
```` 