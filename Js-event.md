### Events caused by page loading

* **Difference between window.onload and document.ready**
http://stackoverflow.com/questions/3698200/window-onload-vs-document-ready

### Events caused by user interaction 

* **blur**   
Lose focus (the user focus on anothe input element)   
http://api.jquery.com/blur/

* **focus_out**   
Lose focusing (with event bubling) detect the lose of focus of parent of an element   
http://api.jquery.com/focusout/

* **click**   
Click on an element it mean    
he click event is only triggered after this exact series of events:   
 The mouse button is depressed while the pointer is inside the element.   
 The mouse button is released while the pointer is inside the element. 
  
> The click event is sent to an element when the mouse pointer is over the element, and the mouse button is pressed and released. Any HTML element can receive this event.

http://api.jquery.com/click/   

* **mouse_down**   
Like a click but more precisely when the mouse is on an element and the button is clicked. 
(Wheras click event, do not need the button to be released on the element)

> The mousedown event is sent when any mouse button is clicked.
http://api.jquery.com/mousedown/

* **submit**   
On form submission do something
http://api.jquery.com/submit/

* **trigger**   
trigger an event on the given element
http://api.jquery.com/trigger/

* **[[scroll]]**
