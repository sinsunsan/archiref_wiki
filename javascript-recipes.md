* **Test if something is undefined**      
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