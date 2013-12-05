http://javascript.crockford.com/code.html

Javascript coding standard for Drupal   
https://drupal.org/node/172169

In most part similar to drupal coding standard for php except

If a function literal is anonymous, there should be one space between the word function and the ( (left parenthesis). If the space is omited, then it can appear that the function's name is function, which is an incorrect reading.

````
    div.onclick = function (e) {
        return false;
    };

    that = {
        method: function () {
            return this.datum;
        },
        datum: 0
    };
````

* **Object creation using prototype**
````
var CarSelector = function(root){ this.init(root); };
	CarSelector.prototype = {
		init:function(root){
			this.root = $(root);
        },
        setHandlers:function(){
			var oThis = this;
			this.inputs.click(function(){
				oThis.ajaxPost();
		        });
                ....
        },


 };
````
