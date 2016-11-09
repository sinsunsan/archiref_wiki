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

### Monitor mongodb query 

http://localhost:28017

will show detail on current operation (if mongod is running on 28017 port)

### Log all queries for debuging 

http://stackoverflow.com/questions/15204341/mongodb-logging-all-queries

One of the solution tell to start mongodb 

```
mongod --profile=1 --slowms=1 &
```
--slowms=1 mean all query are slow query as we give a threhold of 1ms (all query take more time)

Thus the log will be outputed to 
````
/var/log/mongodb/mongodb.log
tail -f /var/log/mongodb/mongodb.log
```
### Do a simple query with ObjectId
So put the "" around the id but not arout ObjectId (which is a js function)
```js
> db.projects. find({_id: ObjectId("5384d7b548836a00007aa1cc")}, {_id: 1})
```

This solution works and actually log the queries.


### Sort by id desc and limit number of document to 5 
```js
 db.bricks.find().sort({_id: -1}).limit(5)
```
