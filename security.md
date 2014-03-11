Security Hole 

* **SQL injection** : Attack where a user input is not correctly filtered and is used to alter a SQL query or even execute other custom queries.
http://en.wikipedia.org/wiki/SQL_injection

* * * Initial query 
* * * ````
* * * "SELECT * FROM users WHERE name ='" + userName + "';"
* * * ````

* * * * When username value is 
* * * ````' or '1'='1'````
* * * ````
* * * SELECT * FROM users WHERE name = '' OR '1'='1';
* * * ````
* * * Select all users as 1 = 1 is always TRUE

* * * * When userName value is 
* * * ````
* * * a';DROP TABLE users; SELECT * FROM userinfo WHERE 't' = 't
* * * ````
* * * ````
* * * SELECT * FROM users WHERE name = 'a';DROP TABLE users; SELECT * FROM userinfo WHERE 't' = 't';
* * * ````
* * * Delete users table and fetch all users informations


