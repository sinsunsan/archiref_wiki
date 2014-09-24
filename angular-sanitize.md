* https://docs.angularjs.org/api/ng/service/$sce
> If your expressions are constant literals, they're automatically trusted and you don't need to call $sce.trustAs on them (remember to include the ngSanitize module) (e.g. <div ng-bind-html="'<b>implicitly trusted</b>'"></div>) just works.

* https://docs.angularjs.org/api/ng/directive/ngBindHtml


So when we have only an object that  contain "static" mix of text + html, **ng-bind-html** is enought. 

When we have an angular expression, we need to use the **$sce.trustAsHtml** service
````js
$scope.page = {
            subheader: {
                options: {
                    title: "VOS REPAS", 
                    text: $sce.trustAsHtml("Consultez vos repas semaine ou repas par repas. <br/> Utilisez les flèches pour naviguer.")
                }
            }
        };
````


