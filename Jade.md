## Jade documentation
* http://jade-lang.com/
* http://naltatis.github.io/jade-syntax-docs/#basics
* https://www.npmjs.org/package/jade-filter

### Jade online converter
* http://naltatis.github.io/jade-syntax-docs/ online jade 2 html converter 
* http://html2jade.vida.io/ With meteor.js, don't escape special character !

### [[jade recipes]]

### [[jade debug]]

### **Extends, mixins, include**   
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

### **Generation in command line**   


* How to automatically watch a set of jade file for changes   
````
jade --watch -P -o /SEB/www/pernod/proto *.jade
````
### Disable attribute mirroring 
https://github.com/visionmedia/jade/issues/1500#issuecomment-40600149

### **Variable scope**   
A variable is defined in the includes 
For extend it's a bit more complicated. 
When you defined variables in the file which is extended (directly of in included) files. This variables will be defined in its scope. 
If in the extended files you define block (which is necessary to taka advantage of extend awesomeness), in you file that is extended this base file, the variables would not be defined.


**The solution to solve this problem**   
https://groups.google.com/forum/#!topic/jadejs/M8WaRKNpcPk    
(and don't oblige to repeat yourself by redefining variable serveral times is 
To create a block var in the layout to be extended, as hight in the html as possible. 
Pass to this block some vars which be used by other blocks