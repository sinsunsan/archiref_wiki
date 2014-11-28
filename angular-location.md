```js
// Hashbang for SEO
angular.module('awesomeModule')
.config(['$locationProvider',
    function($locationProvider) {
        $locationProvider.hashPrefix("!");
    }
```

Just a clarification # is the default      
`$locationProvider.hashPrefix("!");`     
add a ! the # the default so make #!     

This url type     
`http://mgcrea.github.io/angular-strap/##scrollspy`
are set with    
`$locationProvider.hashPrefix("#"); ` 

* # is the default, angular need at least # to identify deep linking part of the url      
* #! is the recommanded pattern named "hash bang"     
To configure it this line is necessary in the above code 
`$locationProvider.hashPrefix("!");`

