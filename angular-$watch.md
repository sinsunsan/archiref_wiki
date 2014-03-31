````
$scope.$watch('form', function(newVal, oldVal){
    console.log('changed');
}, true);
````

#### Tutos
* http://www.bennadel.com/blog/2566-Scope-watch-vs-watchCollection-In-AngularJS.htm
* http://www.benlesh.com/2013/08/angularjs-watch-digest-and-apply-oh-my.html
* http://stackoverflow.com/questions/15112584/using-scope-watch-and-scope-apply

* Trigger a script after angular has triggered    
When triggering a script that need angular to have rendered the page. It's a good pratice to create a directive. 
Like masonry for exemple 
http://jsfiddle.net/uNREn/12/
http://stackoverflow.com/questions/12304291/angularjs-how-to-run-additional-code-after-angularjs-has-rendered-a-template



> When things happen "inside Angular" – e.g., you type into a textbox that has Angular two-way databinding enabled (i.e., uses ng-model), an $http callback fires, etc. – $apply has already been called, so we're inside the "AngularJS" rectangle in the figure above. All watchExpressions will be evaluated (possibly more than once – until no further changes are detected).

> When things happen "outside Angular" – e.g., you used bind() in a directive and then that event fires, resulting in your callback being called, or some jQuery registered callback fires – we're still in the "Native" rectangle. If the callback code modifies anything that any $watch is watching, call $apply to get into the AngularJS rectangle, causing the $digest loop to run, and hence Angular will notice the change and do its magic.