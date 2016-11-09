### saving function, submit on blur, no buttons....

http://jsfiddle.net/slucas/gfpLLrns/

### What is pratically a blur event ? 

http://jsfiddle.net/slucas/unackt5j/

### Trigger input manually

http://jsfiddle.net/NfPcH/27/

A variant with test to make it possible
have several dynamically named e-form
http://jsfiddle.net/slucas/vLqjxr7v/

To be noted, when a e-form attribute is added the normal click and edit behavior don't work automatically. You need to trigger it manually (I spend quite a good time to understand that)

If you e-form is is "testEform1" so you can trigger the editable state 
by 
putting 
testEform1.$show()
or 
testEform1.$hide()


### Ng-repeated test 
http://jsfiddle.net/slucas/p5kru1dy/

Good solution given by library author 
http://jsfiddle.net/NfPcH/22/
https://github.com/vitalets/angular-xeditable/issues/19
