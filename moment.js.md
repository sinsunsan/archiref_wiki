### Changing the locale

http://momentjs.com/docs/#/i18n/
    * change display language 
    * Change national convention (first day of week for example)

### Recipes 

#### Get the last monday, the monday one week ago...

http://momentjs.com/docs/#/get-set/day/
Monday is 1 Sunday is 6 
Previous week monday is -6 

....
* The previous monday from the 29/02/2016
````
$scope.moment().day(1).toString(); 
"Mon Jan 25 2016 11:17:29 GMT+0100"
````
We were the friday 29 at 11:17:29, so moment took the monday at the same time

* The monday one week before
````
$scope.moment('2016-02-29').day(-6).toString(); 
````

### Week number > Date conversion 

* Date > Week number 
Exact conversion 
````
$scope.moment().week();
5
````
Exemple the 29 january
 
* Week > Date 
Take the current date and convert it to its equivalent in a give week of the year
````
$scope.moment().week(11).toDate()
Fri Mar 11 2016 11:11:10 GMT+0100 (CET)
````
