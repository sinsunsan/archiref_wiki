## Libs 

* https://github.com/typicode/json-server Simple automatic Json API server

### HTTP code

*http://www.restpatterns.org/HTTP_Status_Codes/409_-_Conflict

## Docs 
* http://jsonapi.org/format/
* http://www.restapitutorial.com/lessons/whatisrest.html
* http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm

### Test API 
http://requestb.in Allow to test API 

### Rest API standard / Best practices


* http://restcookbook.com/Basics/hateoas/
* http://blog.octo.com/designer-une-api-rest/


## Request Type 

### GET


### POST 

http://stackoverflow.com/questions/23118249/whats-the-difference-between-request-payload-vs-form-data-as-seen-in-chrome
> The Request Payload - or to be more precise: payload body of a HTTP Request - is the data normally send by a POST or PUT Request. It's the part after the headers and the CLRF of a HTTP Request.

> A request with Content-Type: application/json may look like this:

> POST /some-path HTTP/1.1
> Content-Type: application/json

> { "foo" : "bar", "name" : "John" }
> If you submit this per AJAX the browser simply shows you what he is submitting as payload body. That’s all he can do because he has no idea where the data is coming from.

> If you submit a HTML-Form with method="POST" and Content-Type: application/x-www-form-urlencoded or Content-Type: multipart/form-data your request may look like this:

> POST /some-path HTTP/1.1
> Content-Type: application/x-www-form-urlencoded

> foo=bar&name=John
> In this case the form-data is the request payload. Here the Browser knows more: He knows that bar is the value of the input-field foo of the submitted form. And that’s what he is showing to you.

> So, they differ in the Content-Type but not in the way data is submitted. In both cases the data is in the message-body. And Chrome distinguishes how the data is presented to you in the Developer Tools.

