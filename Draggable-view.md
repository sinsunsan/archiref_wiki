To set draggable view up, 
Don't forget to check the permission for the role you want it to user draggable views. 
I've lost so much time undesrtanding why tha handle didn't show !

Secondly, understand the way the sorting value is stored : 
There is two way, the native handler and the cck handler. 
The cck handler is a cck field of the integer type that can store the order and retrieve it. 

The second way is the native handler, which is two tables (in d6) that store the information, view by view. 
It can store more complex things, but it's applicable only to the views used to sort the element. 
The idea is to have a view, with several display, one to show the sorted element, another display to provide a sorting interface. 

1 - Using CCK handler
http://drupal.org/node/283502
The pro of using cck handler is that it's more compatible, the con is that is take more ressources, as it's note just writing in one table