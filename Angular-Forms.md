### Error validations 


* https://scotch.io/tutorials/angularjs-form-validation
* https://docs.angularjs.org/api/ng/directive/input
* http://www.yearofmoo.com/2014/09/taming-forms-in-angularjs-1-3.html#form-validation-in-angular-plus-video

### ngMessage directives

* https://docs.angularjs.org/api/ngMessages

### Better UI form element

* Checkbox and radio buttons forms     
http://scotch.io/tutorials/javascript/handling-checkboxes-and-radio-buttons-in-angular-forms    
https://docs.angularjs.org/api/ng/directive/ngValue

Simple exemple of a jade mixin to test in situ
http://plnkr.co/edit/2cIQYmDXx8gFwZzsN6oA
````jade
//- simple test of input type radios
//- http://plnkr.co/edit/2cIQYmDXx8gFwZzsN6oA
mixin simpleTestInputRadio 
        h2 Which is your favorite ?
          label( ng-repeat="name in names", for="{{name}}" )
            | {{name}}
            input(type="radio"
                   ng-model="my.favorite"
                   ng-value="name"
                   id="{{name}}"
                   name="favorite")
        div You chose {{my.favorite}}
````

### Select list ngOptions 

* http://www.undefinednull.com/2014/08/11/a-brief-walk-through-of-the-ng-options-in-angularjs/