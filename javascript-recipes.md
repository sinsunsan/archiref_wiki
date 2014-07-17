### **Test if something is undefined**      
http://stackoverflow.com/questions/27509/detecting-an-undefined-object-property-in-javascript
````js
if (typeof something === "undefined") {
    alert("something is undefined");
}
````

Contrary to common belief "undefined" is NOT a keyword in javascript, and can in fact have a value assigned to it.
````
`// Degenerate code. DO NOT USE.`
var undefined = false;  // Shockingly, this is completely legal!
if(myVar === undefined) {
 alert("You have been misled. Run away!");
}
````
Additionally, myVar === undefined will raise an error in the situation where myVar is undeclared.

The most robust way to perform this test is:

````if(typeof myVar === "undefined")````
This will always return the correct result, and even handles the situation where myVar is not declared.

***
### **Test the existence of a sub property of an object** 
http://stackoverflow.com/questions/2631001/javascript-test-for-existence-of-nested-object-key
- use try catch to detect and do seomthing with the exeption 
- make a function to detecth the existence of the sub levels
````js
function checkNested(obj /*, level1, level2, ... levelN*/) {
  var args = Array.prototype.slice.call(arguments),
      obj = args.shift();

  for (var i = 0; i < args.length; i++) {
    if (!obj || !obj.hasOwnProperty(args[i])) {
      return false;
    }
    obj = obj[args[i]];
  }
  return true;
}

var test = {level1:{level2:{level3:'level3'}} };

checkNested(test, 'level1', 'level2', 'level3'); // true
checkNested(test, 'level1', 'level2', 'foo'); // false
````
https://gist.github.com/sinsunsan/79981d010e84cb44b681