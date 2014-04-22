* **Get the file name part of an url**   
var fileName = src.substring(src.lastIndexOf('/') +1);     
http://befused.com/javascript/get-filename-url


* **substring**      
Return a substring of a given string       
http://www.w3schools.com/jsref/jsref_substring.asp

* **Comparison of 3 sub string methods**   
http://www.bennadel.com/blog/2159-Using-Slice-Substring-And-Substr-In-Javascript.htm   
````js
String.slice( begin [, end ] )
String.substring( from [, to ] )
String.substr( start [, length ] )
````

* **Replace a substring**   
````js
myString.replace('search', 'replace')
````

* **Make an array from a string with a delimiter**   
````js
var myString = "jhjh,kjhkjh,ioiu'"
myString.split(',');
console.log(myString);
// ["jhjh", "kjhkjh", "ioiu"]
````

* **JSON > String**   
JSON.stringify() JSON > string    
JSON.parse() string > JSON 

````js
var obj = {prop:"lkhjkl", prop1:[11, "kjkj", 45]};
// Object {prop: "lkhjkl", prop1: Array[3]}
var string = JSON.stringify(obj);
// "{"prop":"lkhjkl","prop1":[11,"kjkj",45]}"
var obj1 = JSON.parse(string);
// Object {prop: "lkhjkl", prop1: Array[3]}
````
