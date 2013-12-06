How to adapt :hover effect on touche devices   
http://www.prowebdesign.ro/how-to-deal-with-hover-on-touch-screen-devices/

* **Detection of touch in js**   
```
//test for touch events support and if not supported, attach .no-touch class to the HTML tag.
 
if (!("ontouchstart" in document.documentElement)) {
document.documentElement.className += " no-touch";
}
```

* **How to debug touch behaviors**   
On a mobile of course, 
but also chrome debugger include touche emulation support   
https://developers.google.com/chrome-developer-tools/docs/tips-and-tricks    
Search : "Emulating touch events"
