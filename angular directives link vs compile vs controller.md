### link vs compile vs controller 

* http://stackoverflow.com/questions/12164138/what-is-the-difference-between-compile-and-link-function-in-angularjs
* http://stackoverflow.com/questions/12546945/difference-between-the-controller-link-and-compile-functions-when-definin
* http://www.jvandemo.com/the-nitty-gritty-of-compile-and-link-functions-inside-angularjs-directives/



From http://stackoverflow.com/questions/12546945/difference-between-the-controller-link-and-compile-functions-when-definin
### **compile function**
use for template DOM manipulation (i.e., manipulation of tElement = template element), hence manipulations that apply to all DOM clones of the template associated with the directive. (If you also need a link function (or pre and post link functions), and you defined a compile function, the compile function must return the link function(s) because the 'link' attribute is ignored if the 'compile' attribute is defined.)

### link function

normally use for registering DOM listeners (i.e., $watch expressions on the scope) as well as updating the DOM (i.e., manipulation of iElement = individual instance element). It is executed after the template has been cloned -- e.g., inside an <li ng-repeat...>, the link function is executed after the <li> template (tElement) has been cloned (into an iElement) for that particular <li> element. A $watch allows a directive to be notified of scope property changes (a scope is associated with each instance), which allows the directive to render an updated instance value to the DOM.

### controller function
must be used when another directive needs to interact with this directive. E.g., on the AngularJS home page, the pane directive needs to add itself to the scope maintained by the tabs directive, hence the tabs directive needs to define a controller method (think API) that the pane directive can access/call. 