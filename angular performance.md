#### Links 
* http://www.binpress.com/tutorial/speeding-up-angular-js-with-simple-optimizations/135
* http://stackoverflow.com/questions/18856341/how-can-i-unregister-a-broadcast-event-to-rootscope-in-angularjs
* http://blog.cycle-interactive.com/?p=524
* http://angular-tips.com/blog/2013/08/removing-the-unneeded-watches

## Perfomance best pratice

### [[angular data binding]]

### Remove a event handler on scope $destroy

````js
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
