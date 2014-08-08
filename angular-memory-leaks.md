* http://stackoverflow.com/questions/18856341/how-can-i-unregister-a-broadcast-event-to-rootscope-in-angularjs
* http://blog.cycle-interactive.com/?p=524


````
angular.module('test')
   .controller('QuestionsStatusController2',
   ['$rootScope', '$scope', '$resource', '$state',
   function ($rootScope, $scope, $resource, $state) {

    var cleanUpFunc = $rootScope.$on('action2@QuestionStatusController1', function {
         //write your listener here
    });

    $scope.$on('$destroy', function() {
        cleanUpFunc();
    };

   }]);
````
