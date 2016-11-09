#### Plugins 
* Mongoose search plugin 
http://plugins.mongoosejs.com/

### Mongoose plugins 

* https://www.npmjs.com/package/mongoose-text-search / Text search 
* https://www.npmjs.com/package/mongoose-unique-validator / unique validator
* https://github.com/conancat/mongoose-redis-cache / Redis cache 
* https://github.com/florianholzapfel/express-restify-mongoose / Restify mongoose
* https://github.com/bnoguchi/mongoose-types / Mongoose 2 new types : email & url 

### Relation 
* https://github.com/JamesS237/mongo-relation
* https://github.com/sabymike/mongoose-relationship
* https://www.npmjs.org/package/cascading-relations

### Population 

http://mongoosejs.com/docs/populate.html

* In depth explanation of the population in mongoose 
http://jaketrent.com/post/mongoose-population/

var league;
The author speak of a method to save a new element even with population
```` js
league = {
  display_name: myLeagueName,
  created_by: currentPlayer._id
};

League.create(league, function(err, league) {
  if (err != null) {

  } else {
    return Player.update({
      _id: currentPlayer._id
    }, {
      $push: {
        leagues: league._id
      }
    }, function(err, numberAffected, raw) {
      if (err != null) {

      } else {
        return res.json(league);
      }
    });
  }
});
````
* Problem of saving after having used populate
https://www.npmjs.org/package/cascading-relations

### Virtual field 

Pseudo field to return information that are not stored in mongodb (for example the concatenation of first name + last name)

https://futurestud.io/blog/understanding-virtuals-in-mongoose

### Best pratices

* http://thecodebarbarian.wordpress.com/2013/06/06/61/