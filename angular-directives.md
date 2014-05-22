### Writing a custom directives

* https://docs.angularjs.org/guide/directive
* http://www.sitepoint.com/practical-guide-angularjs-directives/

### Best pratices to create directive

http://www.sitepoint.com/practical-guide-angularjs-directives/

* In order to avoid collisions with some future standard, it's best to prefix your own directive names.
* Unless your template is very small, it's typically better to break it apart into its own HTML file and load it with the templateUrl option.
* When should I use an attribute versus an element? Use an element when you are creating a component that is in control of the template. The common case for this is when you are creating a Domain-Specific Language for parts of your template. Use an attribute when you are decorating an existing element with new functionality.

### Standard directives 

* **[[ngClass]]**     


### Contributed directives 

* Timer, countdown...    
http://siddii.github.io/angular-timer/index.html