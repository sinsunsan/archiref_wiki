### Tuto 
http://www.sitepoint.com/create-a-customized-print-stylesheet-in-minutes/
http://alistapart.com/article/goingtoprint/
http://www.smashingmagazine.com/2011/11/24/how-to-set-up-a-print-style-sheet/


### How to debug print css

Solutions : 
1 * Remove the @media print so that the style apply to the screen display : will give a immediate preview of the print effect. For display: none!important; very straightforward !
* Web developper options : Use the chrome web developper emulator that allwo to quickly swith between screen and print media (and give much more other options to test on mobile devices...)

* http://stackoverflow.com/questions/2452713/suggestions-for-debugging-print-stylesheets
* http://stackoverflow.com/questions/726825/how-do-you-debug-printable-css


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

#### Display none some element 

Non essential element to spare ink

### Special print css @page 
https://developer.mozilla.org/en-US/docs/Web/CSS/@page

* Define the print margin
````
@page :left {
margin: 0.5cm;
}

@page :right {
margin: 0.8cm;
}
````
* Define the page orientation
````
@page {
        size: landscape
    }
````


### Twitter boostrap print css (taken from boilerplate)

````
//
// Basic print styles
// --------------------------------------------------
// Source: https://github.com/h5bp/html5-boilerplate/blob/master/css/main.css

@media print {

  * {
    text-shadow: none !important;
    color: #000 !important; // Black prints faster: h5bp.com/s
    background: transparent !important;
    box-shadow: none !important;
  }

  a,
  a:visited {
    text-decoration: underline;
  }

  a[href]:after {
    content: " (" attr(href) ")";
  }

  abbr[title]:after {
    content: " (" attr(title) ")";
  }

  // Don't show links for images, or javascript/internal links
  a[href^="javascript:"]:after,
  a[href^="#"]:after {
    content: "";
  }

  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }

  thead {
    display: table-header-group; // h5bp.com/t
  }

  tr,
  img {
    page-break-inside: avoid;
  }

  img {
    max-width: 100% !important;
  }

  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }

  h2,
  h3 {
    page-break-after: avoid;
  }

  // Chrome (OSX) fix for https://github.com/twbs/bootstrap/issues/11245
  // Once fixed, we can just straight up remove this.
  select {
    background: #fff !important;
  }

  // Bootstrap components
  .navbar {
    display: none;
  }
  .table {
    td,
    th {
      background-color: #fff !important;
    }
  }
  .btn,
  .dropup > .btn {
    > .caret {
      border-top-color: #000 !important;
    }
  }
  .label {
    border: 1px solid #000;
  }

  .table {
    border-collapse: collapse !important;
  }
  .table-bordered {
    th,
    td {
      border: 1px solid #ddd !important;
    }
  }

}
````