Looking at open source project settings is very informative to discover grunt plugin and copy some settings 
Like : 

* https://github.com/twbs/bootstrap/blob/master/Gruntfile.js

And some tutorials : 
* http://gruntjs.com/configuring-tasks
* http://thanpol.as/grunt/Managing-large-scale-projects-with-Grunt
* https://oncletom.io/2013/dynamic-grunt-targets-using-templates
* http://dontkry.com/posts/code/grunt-tricks.html

### Configuring grunt with [[Gruntfile.js]]

****

### Grunt plugins 

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