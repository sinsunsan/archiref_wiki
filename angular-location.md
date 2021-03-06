### Standard url vs angular html 5 url 

`www.doogle.com/search?color=blue#apple`

#### Server side url
* **www** subdomain 
* **doogle** domain 
* **com** extension 
* **/search** path 
* **?color=blue** search query 

#### Client side url
* **#apple** anchor link  

In a angular based url the anchor link is the place where angular url are coded. 
The hash part of the url if mimicing the left part of the url 
So we have the same component : 
* path 
* search 
* hash 

`www.doogle.com/search?color=blue#/fruit/apple?taste=1#description`
So the `/fruit/apple?taste=1#description`
is a front end url only using the space of the traditional anchor link     
To differentiate it from a simple anchor, google suggest using "#!" instead of "#"     
So our url will be     
`www.doogle.com/search?color=blue#!/fruit/apple?taste=1#description`

### Compatibility with traditional anchor link
As angular use the anchor link for it's url, the traditional anchor is no more available, or at least it is converted in the new angular system. 
So to have a simple 
www.doogle.com/press#fraise
will be 
www.doogle.com/press#!#fraise

More character for the same thing, but if you want cleaner url look at html5 mode and also to it's constraints.

### Html5 mode 
### Location provider has prefix 

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

`#` is the default, angular need at least # to identify deep linking part of the url      
`#!` is the recommanded pattern named "hash bang"     
To configure it this line is necessary in the above code 
`$locationProvider.hashPrefix("!");`