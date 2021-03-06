### Shorter way to defined default value to function parameters 

```js
type = type || 'lunch';
```
It's like a shorter version of the default ternar syntax 
```js
type = (type) ? type : 'lunch';
```
Another style 
```js
return this.token ? this.token.access_token : undefined;
```
### **Test if something is undefined**  

* Update use instead function from lodash or angular 
* Using a function will avoid == errors....

````
/**
 * @ngdoc function
 * @name angular.isDefined
 * @module ng
 * @kind function
 *
 * @description
 * Determines if a reference is defined.
 *
 * @param {*} value Reference to check.
 * @returns {boolean} True if `value` is defined.
 */
function isDefined(value) {return typeof value !== 'undefined';}
````

    
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
***
### Self executing function 

http://code.tutsplus.com/tutorials/24-javascript-best-practices-for-beginners--net-5399

Rather than calling a function, it's quite simple to make a function run automatically when a page loads, or a parent function is called. Simply wrap your function in parenthesis, and then append an additional set, which essentially calls the function.

````js
(function doSomething() {
   return {
      name: 'jeff',
      lastName: 'way'
   };
})();
````


### test if a property of an object exist exluding inherited properties (through prototypal inheritance)

obj.hasOwnProperty

### Inverse the keys and values of an object (to do mapping)

http://nelsonwells.net/2011/10/swap-object-key-and-values-in-javascript/
````js
var invert = function (obj) {

  var new_obj = {};

  for (var prop in obj) {
    if(obj.hasOwnProperty(prop)) {
      new_obj[obj[prop]] = prop;
    }
  }

  return new_obj;
};
````

### Add element to the end of an array 

http://stackoverflow.com/questions/351409/appending-to-array

**1/ Add values**
````js
arrayName.push('value')
````

**2/ Add arrays**
````js
arrayName = arrayName.concat(newArray1, newArray2, ....);
````

### Function returning a function 
````
var foo = function () {return function (x) { return x+2}};
foo()(3)
-> 5
````

### Used a regex to test a string pattern 

http://www.w3schools.com/jsref/jsref_regexp_test.asp
````js
// store in the variable t the string of the current browser
// "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_2) AppleWebKit/537.75.14 (KHTML, like Gecko) Version/7.0.3 Safari/537.75.14"
var t = window.navigator.userAgent
// Store a regex in p
var p = /safari/i;
// test with the regex 
p.test(t);

````

### Count the number of properties in an object 
Despite arrays, object don't have the lenght property    

http://stackoverflow.com/questions/126100/how-to-efficiently-count-the-number-of-keys-properties-of-an-object-in-javascrip
````
Object.keys(home.plans.pricing.features).length
````
Object.keys return an array of the object properties

## Extract the file name from a path with a regex in js 
filePath = "app/data/json/settings.json"

````
console.log(filepath.replace(/^.*(\\|\/|\:)/, '').replace('.json',''));
````
output = "settings"