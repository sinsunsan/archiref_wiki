### Tuto 

* https://www.airpair.com/angularjs/posts/testing-angular-with-karma
* http://www.ng-newsletter.com/posts/practical-protractor.html

## What is what 
### test runner : the engine that run the test
* http://karma-runner.github.io
* http://angular.github.io/protractor

### Test framework : Assertion library 
* https://www.npmjs.com/package/should
* http://chaijs.com/
* http://mochajs.org/
* http://jasmine.github.io/

*** 
### How to write unit test 


*** 
### How to install a test environment 

* https://github.com/yeoman/generator-karma

***
### Test types

* **E2E test** : test aa normal user, goint to the url, checking something exist....
* **Unit test** : test a portion of code, verifying what we expect, actually suceed
* **black box testing** : equal to E2E, we test the site on the users perspective, not trying to underestand what is behing 

### Inside a test spec

* test : named test describe('angularjs homepage', function() {
* assertion : named expectation of what the test should give it('should greet the named user', function() {

### Angular modules used for unit testing 

* https://docs.angularjs.org/api/ngMock

## E2E Test (Test in a browser) as a user would do 

Automate the way you do, when you are manually testing

http://angular.github.io/protractor/#/

## Units test > Karma 

http://karma-runner.github.io/0.12/index.html


### Main 

http://karma-runner.github.io

For compatibility problem with [[phantomjs]] see 
https://github.com/karma-runner/karma-phantomjs-launcher/issues/10