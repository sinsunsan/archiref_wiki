* (**_.contains**)[https://lodash.com/docs#includes]
(Haystack, Needle)
Check if an element is present in a collection, and return true or false

* **_.groupBy** https://lodash.com/docs#groupBy
Allow to regroup content by one of its property, for example image of a collection... where collection is a field of an image content 

* **_.filter** https://lodash.com/docs#filter
Return all elements that the predicate return truthy for.... So always an array of elements even if there is one or zero result 
contrary to _.find, that return the first element and return only one element


### Chaining with lodash 

2 equivalent methods > Chaining is much more easy to read and edit 

```` js
// Wrapper version 

_.each(data.teams, function(team) {
    tableData.push(getTableRow(team, 'teams'));
    // Users
    if (team.users && _.isArray(team.users)) {
        _.each(team.users, function(user) {
            tableData.push(getTableRow(user, 'users'));
            // Projects
            if (user.projects && _.isArray(user.projects)) {
                _.each(user.projects, function(project) {
                    tableData.push(getTableRow(project, 'projects'));
                });
            }
        });
    }
});
// Chained version 
_.chain(data.teams)
.each(function(team) {
    tableData.push(getTableRow(team, 'teams'));
})
.each(function(user) {
    tableData.push(getTableRow(user, 'users'));
})
.each(function(project) {
    tableData.push(getTableRow(project, 'projects'));
})
.value();
````