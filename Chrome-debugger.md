https://developers.google.com/chrome-developer-tools/docs/tips-and-tricks

### Source 

Allow to list all js script.   
First use source tab to see only js script loaded from your domain and other domains. 
 
Options at the bottom    
**beautyfier** : indent javascript code to increase readability    
**pause on exception** : if there is an error pause.    
**Console** : write a javascript code in console   

* Right panel, the step by step debugger toogle a right arrow to activate all break point or descativate all break points

### Stop a browser loading process

Juste hit **Escape**

### Network 

Network are logged only if a page is loaded when the network tab is active.     
It load all http request included ajax call and ajax retrieved js 

* The "sens interdit" button allow to clear all logged file for example, when after an ajax call, news request has been made. 


### Clear cache

CMD + SHIFT + R 
On mac

### Settings 

* Disable cache 
* Simulate touche events
* Emulate other user agent 
* Search a string in all files loaded ! 
CMD + Opt + F in dev tools 

### Breakpoints

Event listener breakpoints   

* **How to localize the cause of a specific event**     
Place a listener on a specific event, then trigger the event
and look at the call stack (source tab). 
You should localize the script and line responsible for this event   

The problem is that when we are using jquery, it's jquery that appear and not our script :(