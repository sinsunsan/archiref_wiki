* [[javascript replace]]
* [[RegExp : regular expression]]
* **[[Drupal and javascript]]**
* **[[Javascript method]]**

http://api.drupal.org/api/drupal/developer!topics!javascript_startup_guide.html/6#oop

* **How to debug javascript**   
http://www.webmonkey.com/2010/02/javascript_debugging_for_beginners/


* **Debug an array in javascript**

Add this   
 console.log(s);  
In the javascript code. 
The result of the debug will be visible in the debugger in chrome or mozilla

To know what is the code of a method (function), you can do it directly in the console   
console.log($.cookie);  

* **Add break point in console**

It's possible to add break point with chrome of firebug, interupt the script, and know the value of every variables at each step

* **Example of an object initialization**

```js
var Drupal = Drupal || { 'settings': {}, 'behaviors': {}, 'themes': {}, 'locale': {} };
```
In this code, Drupal is an Object declared to be equal to itself, or, if not yet set, equal to { 'settings': {}, 'behaviors': {}, 'themes': {}, 'locale': {} } which is an Object containing 4 methods (settings, behaviors, themes, and locale) each of which is itself an Object. This line of code is an Object Initializer.