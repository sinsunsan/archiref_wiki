* $broadcast -- dispatches the event downwards to all child scopes,
* $emit -- dispatches the event upwards through the scope hierarchy.

http://stackoverflow.com/questions/14502006/scope-emit-and-on-angularjs

### Tuto 
* http://toddmotto.com/all-about-angulars-emit-broadcast-on-publish-subscribing/
* special case controller > directive with broadcast
http://jsfiddle.net/smaye81/q2hbnL5b/6/

### $emit vs $broadcast 

* http://stackoverflow.com/questions/11252780/whats-the-correct-way-to-communicate-between-controllers-in-angularjs/19498009#19498009
* http://jsperf.com/rootscope-emit-vs-rootscope-broadcast

### $rootScope.$emit / $rootScope.$on 

Best method for http://stackoverflow.com/questions/11252780/whats-the-correct-way-to-communicate-between-controllers-in-angularjs/19498009#19498009
because no event bubbling, but necessity to un register when the scope is destroyed to prevent creating memory leaks