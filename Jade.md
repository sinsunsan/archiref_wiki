### Jade documentations 
http://jade-lang.com/

**Extends, mixins, include**   
http://tjholowaychuk.com/post/7590787973/jade-mixins-includes       
http://www.devthought.com/code/use-jade-blocks-not-layouts   

Option -P to have pretty indented html   
-o to defined the output directory   
```
jade -P -o /SEB/www/pernod/proto home1.jade
```

To watch the changes of a file    
```
jade -P --watch -o /SEB/www/pernod/proto home1.jade 
```
As we only put one file, it will not watch the change of included files

**JADE Syntax**   

* How to have a for loop to generate a number of element   
```
  - for (var i = 0; i < 5; ++i) {
    #post + i
    img.img_bloc_hp(src='datas/img/vignette_16_9_480px.jpg')
  - }
```
Note the - sign that tell jade that it's not html but javascript code

* How to print a dynamic class or id name    
```
  - for (var i = 0; i < 5; ++i) {
    -var id=[ 'post' + i]
    div(id=id) Lorem ispsum
    img.img_bloc_hp(src='datas/img/vignette_16_9_480px.jpg')
  - }
```
We defined a javascript variable : -var id=[ 'post' + i]   
Than then is used in the id definition : -var id=[ 'post' + i]   

* Non intuitive solution for input checkbox 
```
input.checkbox(type='checkbox') 
  | Check me please !
```
We can't do 
```
input.checkbox(type='checkbox') Check me please !
```
Because input html element can't have child because they are self closing 
See 
https://github.com/visionmedia/jade/issues/445
