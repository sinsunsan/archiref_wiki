#### Links 
* http://www.binpress.com/tutorial/speeding-up-angular-js-with-simple-optimizations/135
* http://stackoverflow.com/questions/18856341/how-can-i-unregister-a-broadcast-event-to-rootscope-in-angularjs
* http://blog.cycle-interactive.com/?p=524
* http://angular-tips.com/blog/2013/08/removing-the-unneeded-watches
* https://www.airpair.com/angularjs/posts/angularjs-performance-large-applications
* https://toddmotto.com/angular-one-time-binding-syntax/
* https://ng-perf.com/

## Perfomance best pratices

* Ng-bind is faster (x2) than {{}} interpolation 
* one time binding


### Performance module 

* https://github.com/ansukla/ng-perf / Allow to do a directive bound digest instead of a full page digest

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


#### Lazy loading of module 

$ocLazyLoad + Ui router config 
```` js
// Form Tools
        .state('formtools', {
            url: "/form-tools",
            templateUrl: "views/form_tools.html",
            data: {pageTitle: 'Form Tools'},
            controller: "GeneralPageController",
            resolve: {
                deps: ['$ocLazyLoad', function($ocLazyLoad) {
                    return $ocLazyLoad.load([{
                        name: 'MetronicApp',
                        insertBefore: '#ng_load_plugins_before', // load the above css files before '#ng_load_plugins_before'
                        files: [
                            '../../../assets/global/plugins/bootstrap-fileinput/bootstrap-fileinput.css',
                            '../../../assets/global/plugins/bootstrap-switch/css/bootstrap-switch.min.css',
                            '../../../assets/global/plugins/jquery-tags-input/jquery.tagsinput.css',
                            '../../../assets/global/plugins/bootstrap-markdown/css/bootstrap-markdown.min.css',
                            
                        ] 
                    }]);
                }] 
            }
        })   

```` 