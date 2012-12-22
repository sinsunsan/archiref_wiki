Only myisam table accept repair command to localize them run this command
```
SELECT TABLE_NAME, ENGINE
FROM information_schema.TABLES
WHERE TABLE_SCHEMA = 'd6_archiref_prod' AND ENGINE = "MyISAM"
```
MyIsma database table has a repair command
```
REPAIR TABLE `tablename`;
```
