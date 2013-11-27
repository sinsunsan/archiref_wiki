Display the scroll position for debugging every time we scroll
```` js
$(window).scroll(function () { 
    console.log("Current scrolltop : " + $(window).scrollTop() + " px");
});
````
