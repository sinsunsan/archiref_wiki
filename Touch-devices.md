How to adapt :hover effect on touche devices   
http://www.prowebdesign.ro/how-to-deal-with-hover-on-touch-screen-devices/

* **Detection of touch in js**   
```
//test for touch events support and if not supported, attach .no-touch class to the HTML tag.
 
if (!("ontouchstart" in document.documentElement)) {
document.documentElement.className += " no-touch";
}
```
