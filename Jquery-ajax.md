
See more at: 
http://deano.me/2012/09/jquery-load-css-with-ajax-all-browsers/#sthash.puSfWAIS.dpuf
* *Load css with ajax*  
```
$.ajax({
  url:"style.css",
  dataType:"script",
  success:function(data){
    $("<style></style>").appendTo("head").html(data);
   //loading complete code here
  }
});
```
