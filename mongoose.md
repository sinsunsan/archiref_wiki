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

### Best pratices

* http://thecodebarbarian.wordpress.com/2013/06/06/61/