### Tuto
https://www.lullabot.com/blog/article/creating-simple-chrome-extension
http://www.phase2technology.com/blog/so-you-want-to-build-a-chrome-extension/

### Chrome extension concepts

* Event page    
https://developer.chrome.com/extensions/event_pages

* Background :
Background task that don't need to change the page  
> If you’re doing some fancy stuff behind the scenes that doesn’t need to inject as much code into individual pages, you’ll probably be looking more at the background.js script (or a renamed version of it).

* Popup : 
Action that can be triggered inside the popup that show when we click on the action button
> If you’re mainly targeting a browser or page action button, you’ll be dealing with popup.html and popup.js. This is really quite simple, since the popup is nothing more than a regular old .html file which references CSS or JS as needed, and is displayed in a small window. Regular front end development rules apply here, and you’re only limited by your imagination, so you can do fancy stuff like AJAX calls or responsive layouts without jumping through any special hoops. Browser actions also give you the ability to add text in front of the button, using the setBadgeText() function, or do something besides show a popup HTML page when clicked. They’re pretty flexible little guys.    

* Content script : 
Css and js that is executed in the viewed page and change it's display and behavior

> If you’re trying to alter the behavior of existing web pages, by adding JS or CSS to them, then you’re going to be spending most of your time in content scripts. You’ll probably want to rename the default “contentscript.js” file (both the file itself and the reference to it in manifest.json), and/or create some new files so that you can better organize your code. Content scripts are very easy to grasp because they literally just run code inside the web pages that you give them access to. The only difference between them and actual JS files included in the page is that content scripts have a couple limitations (see the next section).

### Chrome javascript API 

https://developer.chrome.com/extensions/api_index

### See the code of other chrome extensions

How to see the code of a chrome extension    
https://chrome.google.com/webstore/detail/chrome-extension-source-v/jifpbeccnghkjeaalbbjmodiffmgedin/related?hl=en

https://developer.chrome.com/extensions/devguide    
https://developer.chrome.com/extensions/manifest   

### Start a chrome extension with yeoman

https://github.com/yeoman/generator-chrome-extension

> Would you like to use UI Action? This is where some Chrome extension API lingo comes into play. You can choose “Browser”, “Page”, or “None”, based on whether it’s useful for your extension or not.
> A “Browser” action means it will give you a little button to the right of the address bar

http://www.phase2technology.com/blog/so-you-want-to-build-a-chrome-extension/

````yo chrome-extension --compass````