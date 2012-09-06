* **array_filter**
http://php.net/manual/fr/function.array-filter.php   
Allow to filter an array by a custom function that return the value to keep,   
and if no function is given, it'll filter out FALSE value ('' , FALSE , 0 , NULL) 

* **array_shift**
http://fr2.php.net/array_shift   
array_shift() shifts (remove) the first value of the array off and returns it, shortening the array by one element and moving everything down. All numerical array keys will be modified to start counting from zero while literal keys won't be touched. Return the shifted value.

* **array_flip**   
http://php.net/manual/en/function.array-flip.php   
Allow to flip an array so that value become key and vice-versa
```
$array = array(
 '1' => 'value1',
 '2' => 'value2',
);
$array_flipped = array_flip($array);
print_r($array_flipped);
```
Display
```
array(
 'value1' => 1,
 'value2' => 2 
);

```
