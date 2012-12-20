* **requêtes imbriquées**
The result of the second query is used as a selector of the first one  
``` 
SELECT * FROM node
WHERE nid NOT IN(
SELECT entity_id 
FROM field_data_field_qr_status
```
 