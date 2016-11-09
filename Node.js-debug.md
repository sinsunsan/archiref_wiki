New article and alternative to node inspectors 
* https://mattdesl.svbtle.com/debugging-nodejs-in-chrome-devtools

***

* https://spin.atomicobject.com/2015/09/25/debug-node-js/
* https://github.com/node-inspector/node-inspector
Allow to have a in browser debugger;
start node inspector with a custom port 

```node-inspector  --web-port=8181 server.js``` 

When we type this command it display 

```http://127.0.0.1:8181/?ws=127.0.0.1:8181&port=5858```

Just type this url in a tab of your browser and wait a long time as node inspector need to load all used files including node_modules directory, it can take 10 minutes...

When the loading process is over it will show the debug as though we had typed
```node server.js```