http://net.tutsplus.com/tutorials/javascript-ajax/5-ways-to-make-ajax-calls-with-jquery/   
See more at: 
http://deano.me/2012/09/jquery-load-css-with-ajax-all-browsers/#sthash.puSfWAIS.dpuf
* *Load css with ajax*  
```
$.ajax({
  url:"style.css",
  dataType:"script",
  success:function(data){
    $("head").append("<style>" + data + "</style>");
   //loading complete code here
  }
});
```