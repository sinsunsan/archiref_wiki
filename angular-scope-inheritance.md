* http://lostechies.com/gabrielschenker/2013/12/10/angularjspart-3-inheritance/

* changes with the controller as syntax
http://codetunnel.io/angularjs-controller-as-or-scope/

## With app.run, we can define some variable that is useful  form all controllers 
```
.run(function (DS) {
    // We don't register the "User" resource
    // as a service, so it can only be used
    // via DS.<method>('user', ...)
    // The advantage here is that this code
    // is guaranteed to be executed, and you
    // only ever have to inject "DS"
    DS.defineResource('user');
  })
```