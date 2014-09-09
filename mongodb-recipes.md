### Do a fuzzy search 

http://ilearnasigoalong.blogspot.fr/2013/10/efficient-techniques-for-fuzzy-and.html

### Filters which fields are returned 

Return only the _id    
1 stands for true
The first {} is empty but can include some search parameters
First {} is the equivalent of WHERE SQL clause 
second {} is the equivalent from the SELECT sql clause.
```js
db.projects.find({}, {_id:1});
```

### Return fields that exist 

So we pass to the field name, a object with $exists as property and true as value.
```js
db.bricks.find({project: {$exists: true}}, {_id: 1, project: 1});
```
