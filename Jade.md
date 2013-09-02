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