#### Service vs Factory vs Provider 
*http://stackoverflow.com/questions/15666048/service-vs-provider-vs-factory
* http://tylermcginnis.com/angularjs-factory-vs-service-vs-provider/

http://stackoverflow.com/questions/13937318/convert-angular-http-get-function-to-a-service



SERVICE	DESCRIPTION

http://henriquat.re/basics-of-angular/services-dependency-injection/services-and-dependency-injection-in-angularjs.html

* $http	Allows promise-based access to HTTP requests (API Reference: ng.$http). You can read more about promises in Promises instead of Callbacks (Please note: this chapter has not yet been released).
* $resource	Provides a higher-level abstraction for accessing REST-style services (API Reference: ng.$resource)
* $document	Is a jQuery (lite)-wrapped reference to window.document (API Reference: ng.$document)
* $window	Is a jQuery (lite)-wrapped reference to window (API Reference: ng.$window)
* $timeout	This is a wrapped version of window.setTimeout. In tests, you can use $timeout.flush() to synchronously execute all scheduled timeouts. (API Reference: ng.$timeout)
* $parse	Parses Angular expressions (for example, for binding with ng-model or similar) and provides accessor functions (API Reference: ng.$parse)
* $cacheFactory	Usually used by other services whenever they need a scoped cache of elementes (API Reference: ng.$cacheFactory)
* $filter	Provides programmatic access to a filter function (API Reference: ng.$filter)