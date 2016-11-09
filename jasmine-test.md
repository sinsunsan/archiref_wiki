* **Tutorial**

http://blog.codeship.io/2013/07/30/testing-tuesday-16-javascript-testing-with-jasmine.html
http://code.tutsplus.com/tutorials/testing-your-javascript-with-jasmine--net-21229

* **Matchers**  
  * https://github.com/pivotal/jasmine/wiki/Matchers
  * **toEqual** Check if the expression passed in expect() is equal to another value 
  * **toBeFalsy** The expression is false
  * **.not** inverse the expression (to be placed between expect and the value we expect)
  * **spyOn** watch a property
  * **toHaveBeenCalledWith** check the argument used with a function call
  * **toThrow** check if the function throw an error

````
expect(fn).toThrow(e);
expect(instance).toBe(instance);
expect(mixed).toBeDefined();
expect(mixed).toBeFalsy();
expect(number).toBeGreaterThan(number);
expect(number).toBeLessThan(number);
expect(mixed).toBeNull();
expect(mixed).toBeTruthy();
expect(mixed).toBeUndefined();
expect(array).toContain(member);
expect(string).toContain(substring);
expect(mixed).toEqual(mixed);
expect(mixed).toMatch(pattern);
````

* **Helpers**  
 * **beforeEach()** Allow to run common code before each it() block  


* Additional matcher
https://github.com/JamieMason/Jasmine-Matchers