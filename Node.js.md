* Exports in modules   
http://openmymind.net/2012/2/3/Node-Require-and-Exports/

* Styling convention   
https://github.com/felixge/node-style-guide

* What is NODE_ENV    
http://www.hacksparrow.com/running-express-js-in-production-mode.html
To set a server in production mode, the only thing to do is typing ````export NODE_ENV=production````
To have it saved when the server restart
````
$ echo export NODE_ENV=production >> ~/.bash_profile
$ source ~/.bash_profile
````

* Start Forever in prod mode   
NODE_ENV=production forever start app.js 
