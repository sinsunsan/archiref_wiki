### Docs 

* [Angular docs](http://docs.angularjs.org/api) : Official documentation
* [Ng modules](http://ngmodules.org/) : Found contributed angular directives

### Tutos   
* [Everything you need to understand to start with AngularJS](http://stephanebegaudeau.tumblr.com/post/48776908163/everything-you-need-to-understand-to-start-with)  

### [[Angular Recipes]]

### Angular concepts   
* [[angular controllers]] / Define the application logic (Controller part of MCV)   
* [[angular services]] / Relation with web services and databases (Model part of MVC)   
For example, define an objects that is linked (binded) to a webservice   
* [[angular views]] / Templating (View part of MVC)   
This part is really important in angular, as it trigger the behavior, and define with custom argument of html tags, which js controllers control which part of the page   

* [[angular directives]] 
* [[angular filters]] / Allow to filter string to display it    
For example currency filter to display currency symbol

* [[angular $watch]] / Watch changes in the model   

### Important core directives
* [ngInclude](http://docs.angularjs.org/api/ng.directive:ngInclude)
Include external Html / Is used for example to load a different page. 
* [ngController](http://docs.angularjs.org/api/ng.directive:ngController) 
Define the controller who is in charge of the following chunk of html  
 
* ngInit / Function to be launched immediately 
* [ngClick] / Function to be launched when clicking 
* [[ngShow]] / show if the value is true 

### Selected contributed directives
* [[angular Upload]] : Contributed module to upload files 

### Seed apps 

* [[Mean]]
Seed app using [[angular.js]], [[node.js]], [[twitter bootstrap]] ....   
https://github.com/linnovate/mean