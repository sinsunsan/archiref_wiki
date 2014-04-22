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

* Multiline js in jade (work in progress)   
https://github.com/visionmedia/jade/issues/796