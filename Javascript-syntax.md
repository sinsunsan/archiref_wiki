Tuto bien fait en Français, mais parle de toutes les différences avec le php, la portée des variables, fonctions...   
http://braincracking.org/2011/11/16/javascript-3-fondamentaux/   

* **FALSE is false**   
FALSE is php code
In javascript, we need to write false   

* **Variable variable in js**   
```
var page = 'home';
var obj = {'home': {'width': 235, 'height': 233}};
console.log(obj[page].width);
235
```
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