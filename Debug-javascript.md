* **How to debug javascript**   
http://www.webmonkey.com/2010/02/javascript_debugging_for_beginners/
http://www.alsacreations.com/astuce/lire/1436-console-javascript.html

* **Debug an array in javascript**

Add this   
**console.log(s);**
In the javascript code. 
The result of the debug will be visible in the debugger in chrome or mozilla

To know what is the code of a method (function), you can do it directly in the console   
**console.log($.cookie);**

Explanation of console.log here
http://getfirebug.com/logging

* **See an ajax load content in its url**   
Ajax loaded content is being loaded in a given page, but it call a different url. 
It's possible to access this url directly, to have only the ajax loaded content, and possible js files load at the same time. To know this url, you can go to the nework panel of firebug and analyse which url is being called.

* **See js errors in the error log of firebug**   
Firebug have a error log window that display js error, syntax errors....
Chrome does not seem to have an equivalent, go to the menu tools Web developper tools 
MAJ+CTRL+J

* **Add break point in console**   
It's possible to add break point with chrome of firebug, interupt the script, and know the value of every variables at each step

* **Drupal cache is strange !**   
Even if the cache suppose to be off, the cache could still be active. 
drush cc all after every change is a good way to solve this 

* **increment an alert debug function at every file change**   
Put    
alert("my debug1");   
alert("my debug2");   
...   
Every time you change the code, to be sure the latest code is evaluated   

* **user mozilla add on**   
https://addons.mozilla.org/en-US/firefox/addon/javascript-debugger/