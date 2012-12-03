Reference site http://docs.mongodb.org/

### Connect and database select
```
// Connect to mongo
mongo

// Show existing databases 
show dbs

// Use a specific databases 
use databaseName

// Show collections (equivalent of tables in mysql)
show collections
```

```
// Simple query, all result with a specific field value 
db.user_activity.find({"event_type" : "node_published" });

// More complex query, two conditions with a $and operator
// Note that data.node_type is a sub object of data
db.user_activity.find({ $and: [{"event_type" : "node_published" } , {"data.node_type" : "article"}]});

```