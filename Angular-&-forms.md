### Front end form verification angular
* https://scotch.io/tutorials/angularjs-form-validation

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