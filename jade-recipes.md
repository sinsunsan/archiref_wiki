* How to use a json for data in commande line     
https://github.com/visionmedia/jade/issues/833    

````
Option 1

This insane mixin works:

mixin json()
  - var oldbuf = buf; buf = [];
  block
  - var res = JSON.stringify(JSON.parse(buf.join('')));
  - buf = oldbuf;
  != res
You can then call it:

+json().
  [
    {
      "name": "ABC-Logistic",
      "file":  "Abc-logistic",
      "link":  "abc-logistic.co.jp"
    }
  ]
And the resulting file will contain:

[{"name":"ABC-Logistic","file":"Abc-logistic","link":"abc-logistic.co.jp"}]

````

* How to load data in a grunt base environnement    
https://github.com/gruntjs/grunt-contrib-jade#data

````
options: {
                pretty: true, // Output HTML in indented style
                doctype: 'html', 
                data: {
                    links: grunt.file.readJSON("app/Resources/views/mixins/_vars.json"), 
                },
            },

````
#{link.title} will be available   
Potentially we can load seevral data objects   

* Multiline js in jade (work in progress)   
https://github.com/visionmedia/jade/issues/796