### Grunt plugins 

To see all grunt plugins    
https://www.npmjs.org/browse/depended/grunt

And a more intersting list to resort    
http://gruntjs.com/plugins

### grunt autoprefixer
https://github.com/postcss/autoprefixer#browsers
Allow to get rid of compass or bourbon for browser prefix. 
As il will do it for you, so it's possible to get back to prefix free 

### grunt uncss 
Remove unused css 
https://github.com/giakki/uncss      
https://github.com/addyosmani/grunt-uncss-sass-example    

### Grunt Angular templates
https://www.npmjs.org/package/grunt-angular-templates

### Grunt time
Display the time spent on grunt task
https://www.npmjs.org/package/time-grunt

### Grunt jiit 

#### Grunt page speed
https://www.npmjs.org/package/grunt-pagespeed

#### grunt concurrent
https://www.npmjs.org/package/grunt-concurrent
Allow to run several tasks at a time. Typically, the watch and another task nodemon for example

#### [[grunt sass]]   
* https://www.npmjs.org/package/grunt-contrib-compass    
* https://github.com/gruntjs/grunt-contrib-sass

#### [Grunt newer](https://github.com/tschaub/grunt-newer)
Recompile only new files by comparing modifiction date of src / dest

#### grunt usemin

Read html files to list all assets, then run grunt task to modify those assets, finally change the path to optimized new files 
* http://www.youtube.com/watch?v=gIbfDxF69c8
* http://h3manth.com/new/blog/2014/grunt-usemin-example/
* https://github.com/hemanth/grunt-usemin-example
* http://stackoverflow.com/questions/18812126/how-to-update-jade-file-css-js-references-by-grunt-usemin
* https://github.com/bevacqua/usemin-patterns

### grunt CSS comb 
Reorder css rules automatically for readibility 
Use 
https://github.com/twbs/bootstrap/blob/master/less/.csscomb.json
For inspiration

### grunt prettify
Clean up html files with configurations styles options   
https://www.npmjs.org/package/grunt-prettify

### Wiredep 
Automatically put dependency instance, from you bower.json
* https://github.com/taptapship/wiredep
* http://lab.brightnorth.co.uk/2014/08/13/automating-linkage-how-i-learned-to-stop-worrying-and-love-the-build/
* http://colintoh.com/blog/bower-best-served-with-build-tool