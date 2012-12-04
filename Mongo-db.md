Reference site http://docs.mongodb.org/

### Terminology 

**Mongo**       MYSQL   
**Document**  =  Row   
**Collection** = Table   
**Database**  =  Database   


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
### Querying
```
// Simple query, all result with a specific field value 
db.user_activity.find({"event_type" : "node_published" });

// More complex query, two conditions with a $and operator
// Note that data.node_type is a sub object of data
db.user_activity.find({ $and: [{"event_type" : "node_published" } , {"data.node_type" : "article"}]});

// All published node of type q_r authored by user 1
db.user_activity.find({ $and: [{"event_type" : "node_published" } , {"data.node_type" : "q_r"}, {"involved_users" : 1 }]});

```

### Update 
http://docs.mongodb.org/manual/applications/update/