### Advanced technics for grunt file 

Splittint the config, grunt:new, grunt-notify
* http://www.html5rocks.com/en/tutorials/tooling/supercharging-your-gruntfile/?redirect_from_locale=fr

Grunt reload
*http://rhumaric.com/2013/07/renewing-the-grunt-livereload-magic/
#### gruntfile.js examples 

* https://gist.github.com/booleanbetrayal/8541399
* http://blog.pedago.com/2014/01/21/goodbye-sprockets-a-grunt-based-rails-asset-pipeline/

#### Dynamic file object configuration 
http://gruntjs.com/configuring-tasks#building-the-files-object-dynamically


dest will add a prefix to to directory where grunt has found a match starting at cwd
````
files: {
    expand: true, //Enable dynamic expansion.
    cwd: 'myproject/html', // Src are relative to this path
    src: ['**/*.jade'],
    dest: bundleDir,
    dest: 'myproject/html,
    ext: '.html.twig' // will be apended to the original file name without extension
}, 
````
So in the previous code grunt file look at jade file under **myproject/html** dir and put the compiled version in      
**cwd + dir of the jade file relative de cwd + dest**    
So with dest = '' it will a myproject/html/blog/test.jade put them at 
blog/test.html.twig      
with dest = 'myproject/html' it will put them at 
myproject/html/blog/test.html.twig so in the same directory as it's source


#### Globing patterns 

How to match a file without naming them    
http://gruntjs.com/configuring-tasks#globbing-patterns
````
 src: ['**/*.jade', '!**/_*.jade'],
````
jade files under all sub directories, but not starting with _