* **absolute positioning inside a div**   
For example to position a submit button inside a form element
The absolute positioning of the child (the submit button)
Works when its parent is relative positioning (per aps in absolute also I've not checked)

* **Keep height / width ratio in a fluid/ responsive design**   
http://stackoverflow.com/questions/5445491/height-equal-to-dynamic-width-css-fluid-layout   
CSS only solution   
http://wellcaffeinated.net/articles/2012/12/10/very-simple-css-only-proportional-resizing-of-elements/
http://jsfiddle.net/wellcaffeinated/8Frb6/
My simple jsFiddle application   
http://jsfiddle.net/slucas/8avcw/

* **Conflict between position: fixed and transform**     
transform and position fixed are not compatible    
http://meyerweb.com/eric/thoughts/2011/09/12/un-fixing-fixed-elements-with-css-transforms/    
When a transform is set on a parent of a fixed div     
This div is positioned as absolute      
http://stackoverflow.com/questions/15194313/webkit-css-transform3d-position-fixed-issue
> "In the HTML namespace, any value other than ‘none’ for the transform results in the creation of both a stacking context and a containing block. The object acts as a containing block for fixed positioned descendants." http://www.w3.org/TR/css3-2d-transforms/#transform-rendering
An attempt to fix the issue    
http://jsfiddle.net/vishl/wzPSF/

* **Style checkbox and radio buttons**    
http://webdesign.tutsplus.com/articles/quick-tip-easy-css3-checkboxes-and-radio-buttons--webdesign-8953

* **Debug a variable value**    
````
@debug "$boolean is #{$boolean}"
````
