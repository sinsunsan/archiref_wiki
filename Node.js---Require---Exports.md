* http://openmymind.net/2012/2/3/Node-Require-and-Exports/

## module.exports vs exports === the same 
* http://www.sitepoint.com/understanding-module-exports-exports-node-js/

`1) Imagine that this line of code exists as the first line of code in greetings.js:`

`// greetings.js`
`var exports = module.exports = {};`

But this line don't need to be added, as this reference is already made by node.js

## module.exports = myfn vs module.exports.myFn = myFn


One export per file or export an object with many properties, functions....  
http://openmymind.net/2012/2/3/Node-Require-and-Exports/