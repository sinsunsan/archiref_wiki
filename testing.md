[[js testing]]

### Advantages of testing 

* **Identify problems early** : when it's not too complicated to fix things. Later the bug can cause other bugs in the program that are much more complicated to find 

* **Facilitate [[refactoring]]** : as when the code change and produce a regression in other part of the code. It's immediately identified and fixed.

* **Provide a complementary [[documentation]]** on the code, which is less prone to be outdated, as the test are actively maintained. Allow to understand what is the expected result, thus understand with more detail, what the developer has done.

### Test types

* **TDD Test Driven Development** : Write the test before to write the code. The test will always fail at first, as the features has not been already implemented. Allow to know precisely which is the target of a projected features. This features is described by a user story.
http://en.wikipedia.org/wiki/Test-driven_development
Advantages testing provide :    
  * Be more confident of the quality of the code 
  * be able to refactor with confidence and be noticed when this breaks a previous code

* **Unit test** : Test that evaluate the validity of a small fragment of code. A complex module can have several unit test. Used in TDD
http://en.wikipedia.org/wiki/Unit_testing

* **Black box testing** : Test methodology where the tester don't care on how a given features is implemented but only it's input and output. He build the test on the specifications that describe what the application is suposed to do.   
http://en.wikipedia.org/wiki/Black_box_testing
