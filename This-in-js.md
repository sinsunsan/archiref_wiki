* http://perfectionkills.com/know-thy-reference/
* http://stackoverflow.com/questions/7234282/what-is-the-reason-for-var-this-this
````
$.fn.doSomethingWithElements = function() {
    var $this = this;

    this.each(function() {
        // `this` refers to each element and differs each time this function
        //    is called
        //
        // `$this` refers to old `this`, i.e. the set of elements, and will be
        //    the same each time this function is called
    });
};
````

* **Call a function with a defined this with apply**   
The apply() method calls a function with a given this value and arguments provided as an array (or an array-like object).   
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply
