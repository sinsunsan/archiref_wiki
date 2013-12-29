[[angular.js]] directive to show an element or not   

* **Display something as soon as we start to type**

Hello + What we type in the input field, is only shown if it has a value, which mean we have started to type. 

```` 
Write some text in textbox:
<input type="text" ng-model="sometext" />
<h1 ng-show="sometext">Hello {{ sometext }}</h1>```
```` 

***

* **Use the result of an expression to show or not show a result**
If the user is not set as "male" we don't show it. 
We could also set this condition in the database call, but this  way, we can easily filter between male and female for example using the same set of datas.

```` 
<div data-ng-repeat="user in users" , data-ng-show="user.gender == "male" > 
  <h2>{{user.name}}</h2>
  <div>{{user.desc}}</div>
</div>

```` 
