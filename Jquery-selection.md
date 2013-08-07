* **Select several DOM element that are not of the same type**   
This code select html but also body   
```$('html, body');```

* **eq** Return a given sub object by its index n°
$('li').eq(2); // The third li

* **$.merge()** Allow to merge two things like 2 jquery objects  
http://api.jquery.com/jQuery.merge/
````
var previous = $(this).prev('td');   
var next = $(this).next('td');   
var all = $.merge(previous, next);   
````
