* http://docs.angularjs.org/api/ng/directive/ngClass   
* https://coderwall.com/p/r3_geg   
* My tests http://jsbin.com/tatux/3/   
* http://stackoverflow.com/questions/7792652/what-is-the-best-way-to-conditionally-apply-a-class-with-angularjs

**Use cases**
 
### Printing a unique class Name 
    
in the html > ```ng-class="scopeVarName"```   
in the controller > ```$scope.scopeVarName = 'blue';```   
in the css ```.blue { color: blue; }```

### Concatenate a static part + a dynamic part as the class name 

http://stackoverflow.com/questions/14024448/expression-inside-ng-class  