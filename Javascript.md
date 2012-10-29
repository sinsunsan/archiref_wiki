* [[javascript replace]]
* [[RegExp : regular expression]]
* **[[Drupal and javascript]]**
* **[[Javascript method]]**
* **[[debug javascipt]]**

* **Example of an object initialization**

```js
var Drupal = Drupal || { 'settings': {}, 'behaviors': {}, 'themes': {}, 'locale': {} };
```
In this code, Drupal is an Object declared to be equal to itself, or, if not yet set, equal to { 'settings': {}, 'behaviors': {}, 'themes': {}, 'locale': {} } which is an Object containing 4 methods (settings, behaviors, themes, and locale) each of which is itself an Object. This line of code is an Object Initializer.