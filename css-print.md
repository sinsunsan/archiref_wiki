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

### Things to change 
#### Px to point 
````

Pixels => Points
6px => 5pt
7px => 5pt
8px => 6pt
9px => 7pt
10px => 8pt
11px => 8pt
12px => 9pt
13px => 10pt
14px => 11pt
15px => 11pt
16px => 12pt
17px => 13pt
18px => 14pt
19px => 14pt
20px => 15pt
21px => 16pt
22px => 17pt
23px => 17pt
24px => 18pt
````
### Special print css @page 
https://developer.mozilla.org/en-US/docs/Web/CSS/@page

### How to debug print css

Solutions : 

* Web developper options : but don't works with @media print
* Firebug option

http://stackoverflow.com/questions/2452713/suggestions-for-debugging-print-stylesheets
http://stackoverflow.com/questions/726825/how-do-you-debug-printable-css