* target only mozilla 
````
@-moz-document url-prefix() { 
  .selector {
     color:lime;
  }
}
````

* liste of browser hack     
http://borishoekmeijer.nl/how-to-target-a-specific-browser



*** 

Browser detection in angular 
http://stackoverflow.com/questions/22947535/how-to-detect-browser-using-angular
````js
app.service('browser', ['$window', function($window) {

     return function() {

         var userAgent = $window.navigator.userAgent;

        var browsers = {chrome: /chrome/i, safari: /safari/i, firefox: /firefox/i, ie: /internet explorer/i};

        for(var key in browsers) {
            if (browsers[key].test(userAgent)) {
                return key;
            }
       };

       return 'unknown';
    }

}]);
````