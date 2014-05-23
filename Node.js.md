* [[package.json]] // The package.json list all node modules that are needed for a project 

* install node.js as a user (and no root)
http://increaseyourgeek.wordpress.com/2010/08/18/install-node-js-without-using-sudo      
On mac easier to install first brew on a different directory 
http://lolindrath.com/blog/2011/09/13/hombrew-from-home-directory/

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

* Start a server with grunt in a given environment     
NODE_ENV=development grunt
