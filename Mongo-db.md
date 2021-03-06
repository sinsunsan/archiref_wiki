Reference site http://docs.mongodb.org/

* [[mongoose]]
* [[mongodb recipes]]

### Tuto 

http://snmaynard.com/2012/10/17/things-i-wish-i-knew-about-mongodb-a-year-ago/

### client 

http://robomongo.org/

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

```
// Modify status field in a entity with id 23715
db.user_activity.update({ "entity_id" : 237515 } , { $set : {"status" : 1}});

```

### Backup 

Mongodump a integrated dump utility > export binary files
* http://docs.mongodb.org/manual/tutorial/backup-with-mongodump/
* http://www.thegeekstuff.com/2013/09/mongodump-mongorestore/

Mongoexport > export json files
* http://docs.mongodb.org/manual/reference/program/mongoexport/#bin.mongoexport

### Connection and client  
*https://scotch.io/quick-tips/connecting-to-mongodb-using-robomongo