A bunch of angular recipes     
https://leanpub.com/recipes-with-angular-js/read

* **Print a class name depending of the value of a variable**   
http://stackoverflow.com/questions/14735257/what-angularjs-expression-syntax-is-this-in-ng-class

* **Click to edit a field**   
http://icelab.com.au/articles/click-to-edit-with-angularjs/   
http://icelab.com.au/articles/levelling-up-with-angularjs-building-a-reusable-click-to-edit-directive/

* **Change the url without reloading the page**   
http://stackoverflow.com/questions/18337093/updating-url-in-angular-js-without-re-rendering-view   
But have the page reloaded for specific cases   
http://stackoverflow.com/questions/19137504/force-angularjs-to-reload-a-route-although-option-reloadonsearch-is-set-to-false

* **Change the display only when the services have returned their data to prevent the flicker effect**   
http://stackoverflow.com/questions/11972026/delaying-angularjs-route-change-until-model-loaded-to-prevent-flicker?rq=1

* **Combine different app / module in the same page**   
http://stackoverflow.com/questions/12860595/how-to-define-two-angular-apps-modules-in-one-page   
http://www.simplygoodcode.com/2014/04/angularjs-getting-around-ngapp-limitations-with-ngmodule

* **Toogling the visibility of an element**    
http://geniuscarrier.com/ng-toggle-in-angularjs/
http://jsfiddle.net/geniuscarrier/tKZjZ/55/

* **Angular hash route and real hash**   
````
http://localhost:18080/equipe#!/#blocHistory
````
In this url #! is the hash + bang used by angular, the path is / and the real plain hash is #blocHistory

* **Object and object properties** 

Example of handling of all properties and some properties of an object 
**search.$** @todo learn more about
````js
Any: <input ng-model="search.$"> <br>
Name only <input ng-model="search.name"><br>
Phone only <input ng-model="search.phone"><br>
````
https://docs.angularjs.org/api/ng/filter/filter

* **Filter results for non null value of a field** 
To filter for result that have null field you can do 
````
ng-repeat="aliment in dated.aliments | filter: {ingredient_id: null}"
````
But how to do for non null field ?
There is a small syntax for that
````
ng-repeat="aliment in dated.aliments | filter: {ingredient_id: '!!'}"
````

http://jsfiddle.net/TheSharpieOne/RGEdc/