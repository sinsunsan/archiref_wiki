* [[javascript control structures]]   
* [[javascript lint]]

* **user strict**    
http://stackoverflow.com/questions/1335851/what-does-use-strict-do-in-javascript-and-what-is-the-reasoning-behind-it    
New mode of interpretation of javascript to remove bad features, apply to the file, or to a function     
`'use strict';`

Tuto bien fait en Français, mais parle de toutes les différences avec le php, la portée des variables, fonctions...   
http://braincracking.org/2011/11/16/javascript-3-fondamentaux/   

* **FALSE is false**   
FALSE is php code
In javascript, we need to write false   

***

* **Variable variable in js**   
```
var page = 'home';
var obj = {'home': {'width': 235, 'height': 233}};
console.log(obj[page].width);
235
```

***

* **var to define a variable with a local scope**   
var i = 1; create the i variable and its value is only available the first time, it's set.
More precisely, this variable has its value inside the function it has been created, and in the function this function is calling, but not before.   
This way there'll not be variable collabpse. If ommited the variable scope is global.

```
test1 = function() {
	var x = 1;
	test2 = function() {
		var x = 2;
		test3 = function() {
			var x = 3;
			console.log(x); // 3
		}();
	}();
	console.log(x); // 1
}();
console.log(x); // undefined
```

***

* **isolate the code**   
To be sure not to have variable collapse always embed the code in 
```
(function() { 
}()) 
```
In drupal it's   
```
(function ($) {
...
})(jQuery);
```

***
* **Two methods to access an object properties**
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Member_Operators

***

* **Found in a code** May be a best practice, need to be checked

````
// the semi-colon before function invocation is a safety net against concatenated
// scripts and/or other plugins which may not be closed properly.
;(function ( $, window, document, undefined ) {

	// undefined is used here as the undefined global variable in ECMAScript 3 is
	// mutable (ie. it can be changed by someone else). undefined isn't really being
	// passed in so we can ensure the value of it is truly undefined. In ES5, undefined
	// can no longer be modified.

	// window and document are passed through as local variable rather than global
	// as this (slightly) quickens the resolution process and can be more efficiently
	// minified (especially when both are regularly referenced in your plugin).
````

* Document is the html document, the full dom    
* Window is the global object    
* $ is jquery  

***

* **Declare several variable in one line**    
/* Vars */
````
		var me = this,
			current = ($(window).scrollTop()),
			limit = me.$holder.offset().top,
			islast = sticky.stack[sticky.stack.length-1] == me.$body,
			fixed = (islast)? current >= limit-sticky.offset+me.height : current >= limit-sticky.offset,
			stackit = (!$(me).hasClass('top') && !$(me).hasClass('stripper')),
			keep = ($(me).hasClass('top') || $(me).hasClass('keep')); 
````
