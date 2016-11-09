### How to insert line break with concatenate function
````
=ArrayFormula( CONCATENATE( E1:E3 & CHAR(10) ) )
````

Will concatated all 3 lines separating it with CHAR(10) which is a line break 
````
=ArrayFormula( CONCATENATE( "- "  & E1:E3 & CHAR(10) ) )
````
To make auto prefixing by "- "
````
- dsds
- dsds
- dsdsds
````