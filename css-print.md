### Tuto 
http://www.sitepoint.com/create-a-customized-print-stylesheet-in-minutes/

### Print css

By default, no css is applied to the print version of the page 
````
@media print {
````

Or that 
````
<style type="text/css" media="screen">.uv-icon:hover{opacity:1}</style>
````

Except if a @media print media query is used

### Special print css @page 
https://developer.mozilla.org/en-US/docs/Web/CSS/@page

### How to debug print css

Solutions : 

* Web developper options : but don't works with @media print
* Firebug option

http://stackoverflow.com/questions/2452713/suggestions-for-debugging-print-stylesheets
http://stackoverflow.com/questions/726825/how-do-you-debug-printable-css