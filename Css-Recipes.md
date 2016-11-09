### New menu mobile > cross and full screen mobile menu

http://taostudiodesign.com/about

### **absolute positioning inside a div**   
For example to position a submit button inside a form element
The absolute positioning of the child (the submit button)
Works when its parent is relative positioning (per aps in absolute also I've not checked)

###  **Keep height / width ratio in a fluid/ responsive design**   
http://stackoverflow.com/questions/5445491/height-equal-to-dynamic-width-css-fluid-layout   
CSS only solution   
http://wellcaffeinated.net/articles/2012/12/10/very-simple-css-only-proportional-resizing-of-elements/
http://jsfiddle.net/wellcaffeinated/8Frb6/
http://www.fredparke.com/blog/css-padding-trick-responsive-intrinsic-ratios

My simple jsFiddle application   
http://jsfiddle.net/slucas/8avcw/
http://jsbin.com/ceciraralo/1/

###  **Conflict between position: fixed and transform**     
transform and position fixed are not compatible    
http://meyerweb.com/eric/thoughts/2011/09/12/un-fixing-fixed-elements-with-css-transforms/    
When a transform is set on a parent of a fixed div     
This div is positioned as absolute      
http://stackoverflow.com/questions/15194313/webkit-css-transform3d-position-fixed-issue
> "In the HTML namespace, any value other than ‘none’ for the transform results in the creation of both a stacking context and a containing block. The object acts as a containing block for fixed positioned descendants." http://www.w3.org/TR/css3-2d-transforms/#transform-rendering
An attempt to fix the issue    
http://jsfiddle.net/vishl/wzPSF/

###  **Style checkbox and radio buttons**    
http://webdesign.tutsplus.com/articles/quick-tip-easy-css3-checkboxes-and-radio-buttons--webdesign-8953

###  **Debug a variable value**    
````
@debug "$boolean is #{$boolean}"
````

###  **Keep the footer at the bottom of the page regardeless of the content height**    
http://www.cssreset.com/how-to-keep-footer-at-bottom-of-page-with-css/
http://stackoverflow.com/questions/5189238/how-to-make-a-footer-fixed-in-the-page-bottom

###  Give a percentage dimension minis a fixed dimensions 
We have a full height container height: 100%; 
But we want to soutract a fixed height, of a footer for example height: 120px; 
There is a new css3 function that is decently supporterted calc()
```css
height: calc(100% -50px);
```
* https://developer.mozilla.org/en-US/docs/Web/CSS/calc#Browser_compatibility   
* http://stackoverflow.com/questions/2434602/css-setting-width-height-as-percentage-minus-pixels
* http://caniuse.com/#feat=calc

### Select all element but the first one

```$('.line.days .span-calendar:nth-child(n+2)').hide();```
More nth-child recipes 
http://css-tricks.com/useful-nth-child-recipies/


### Equal height column 
* http://www.vanseodesign.com/css/equal-height-columns/
** http://www.vanseodesign.com/blog/demo/equal-height-columns/offset-columns.php
Border technic to have equal height column
* http://www.minimit.com/articles/solutions-tutorials/bootstrap-3-responsive-columns-of-same-height

### Add a hover border withour make the element move
Use a transparent border for the un hovered element
* http://stackoverflow.com/questions/8625812/css-hover-border-makes-inline-elements-adjust-slightly


### Make a line break only a a defined display size 
The solution use a <br /> that is displayed or not.   
* http://danielmall.com/articles/responsive-line-breaks/

### select item with css depending of their rank order 
http://css-tricks.com/the-difference-between-nth-child-and-nth-of-type/
http://css-tricks.com/how-nth-child-works/
http://codepen.io/sinsunsan/pen/YPXyaV

### Viewport height 

* https://web-design-weekly.com/2014/11/18/viewport-units-vw-vh-vmin-vmax/

