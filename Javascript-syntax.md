http://braincracking.org/2011/11/16/javascript-3-fondamentaux/   

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