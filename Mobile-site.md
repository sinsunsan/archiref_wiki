There is some changes needed when converting to mobile 

* [[Touch devices]]

* Slow scroll on iphone ?   
http://programming.mvergel.com/2013/09/solved-smooth-div-scrolling-in-ipad.html#.U5AvEZR_tGw

> If you have a scrollable div using overflow: auto or overflow: scroll, you will notice that the scroll is slow or choppy. To make the inline scroll smooth, just add the following in your css class:
````css
#SCROLLABLE_DIV {
  height: 300px;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
}
````