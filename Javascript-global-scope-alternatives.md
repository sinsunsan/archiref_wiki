It's bad pratice to throw everything in the window object, which is the global scope in js 
There is alternatives you can find all listed in the book  
[Javascript The good parts](http://www.amazon.com/JavaScript-Good-Parts-Douglas-Crockford/dp/0596517742?archiref-21)

* Define you new functions as a jquery plugin 

```
$.urlParam = function(name){
    var results = new RegExp('[\\?&]' + name + '=([^&#]*)').exec(window.location.href);
    if (results==null){
       return null;
    }
    else{
       return results[1] || 0;
    }
}
```
