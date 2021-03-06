Temmplates are html chunk or partials that are used by : 
* Directives 
* ngInclude 
* ngViewe

There is several way to declare a template to be used. 
## The template cache 

https://docs.angularjs.org/api/ng/service/$templateCache


## Recipes 

* **Change a template url from a ngInclude**    
https://docs.angularjs.org/api/ng/directive/script
````js
<script type="text/ng-template" id="/tpl.html">
  Content of the template.
</script>
<a ng-click="currentTpl='/tpl.html'" id="tpl-link">Load inlined template</a>
<div id="tpl-content" ng-include src="currentTpl"></div>
````
src is changed dynamically by clicking on the a tag 

* **Override a bootstrap UI directives**   
http://stackoverflow.com/questions/17660947/can-you-override-specific-templates-in-angularui-bootstrap

## How directives load templates 
### 1/ Place the template in cache in the same js file


Example with the accordion directive of bootstrap UI 

Declaration of all templates in a module
````js
angular.module("ui.bootstrap.tpls", ["template/accordion/accordion-group.html","template/accordion/accordion.html","template/alert/alert.html","template/carousel/carousel.html","template/carousel/slide.html","template/datepicker/datepicker.html","template/datepicker/day.html","template/datepicker/month.html","template/datepicker/popup.html","template/datepicker/year.html","template/modal/backdrop.html","template/modal/window.html","template/pagination/pager.html","template/pagination/pagination.html","template/tooltip/tooltip-html-unsafe-popup.html","template/tooltip/tooltip-popup.html","template/popover/popover.html","template/progressbar/bar.html","template/progressbar/progress.html","template/progressbar/progressbar.html","template/rating/rating.html","template/tabs/tab.html","template/tabs/tabset.html","template/timepicker/timepicker.html","template/typeahead/typeahead-match.html","template/typeahead/typeahead-popup.html"]);
````

The directive module declare the template module as dependency
````js 
angular.module("ui.bootstrap", ["ui.bootstrap.tpls", "ui.bootstrap.transition","ui.bootstrap.collapse","ui.bootstrap.accordion","ui.bootstrap.alert","ui.bootstrap.bindHtml","ui.bootstrap.buttons","ui.bootstrap.carousel","ui.bootstrap.dateparser","ui.bootstrap.position","ui.bootstrap.datepicker","ui.bootstrap.dropdown","ui.bootstrap.modal","ui.bootstrap.pagination","ui.bootstrap.tooltip","ui.bootstrap.popover","ui.bootstrap.progressbar","ui.bootstrap.rating","ui.bootstrap.tabs","ui.bootstrap.timepicker","ui.bootstrap.typeahead"]);
````
In the directive there is an url as if it where downloaded from the server, though the template is in the js file 
"template/accordion/accordion.html"
````js
angular.module('ui.bootstrap.accordion', ['ui.bootstrap.collapse'])
.directive('accordion', function () {
  return {
    restrict:'EA',
    controller:'AccordionController',
    transclude: true,
    replace: false,
    templateUrl: 'template/accordion/accordion.html'
  };
})
````

````js
angular.module("template/accordion/accordion.html", []).run(["$templateCache", function($templateCache) {
  $templateCache.put("template/accordion/accordion.html",
    "<div class=\"panel-group\" ng-transclude></div>");
}]);
````

### 2/ Output the template in a <script ng-template .. 

It's basically the same that solution 1 
````js
angular.module('wecook.meal_controller', ['backend'])
    .run(['$templateCache', function($templateCache) {
        $templateCache.put('edition_tooltip_breakfast.html', document.getElementById('edition_tooltip_breakfast.html').innerHTML );
}]);
````
Except that we find the template in the html of main document and not in the js file. 
The advantage is that we have a cleaner syntax highlighting without need to escape like in js templating. 
But as it's included in the main document, it's less flexible.

### 3/ Load the template with an ajax call 

Just place the file at the url you specify in the directive, and it will be loaded if available. 

The advantage is the total independance, of the html chunk from the main document, which allow a simple reuse et make the debug easier. 

The drawback can be too much ajax query, that slow down the page loading. 