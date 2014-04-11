* Dynamic file object configuration 
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
So in the previous code grunt file look at jade file under myproject/html dir and put the compiled version at 
cwd + dir of the jade file relative de cwd + dest
So with dest = '' it will a myproject/html/blog/test.jade put them at 
blog/test.html.twig 
with dest = 'myproject/html' it will put them at 

myproject/html/blog/test.html.twig so in the same directory as it's source