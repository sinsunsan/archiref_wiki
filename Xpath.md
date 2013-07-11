Is a selection language, like jquery in javascript. 
Works with xml documents and a subset of xml which are html docs

Could try with this xml feeds of events in the region Auvergne   
http://www.letransfo.fr/layout/set/xml/agenda/view/xml/1

### Basics
http://www.w3schools.com/xpath/

* all is nodes with parents / childs relation ships
http://www.w3schools.com/xpath/xpath_nodes.asp

* Selection syntax 
http://www.w3schools.com/xpath/xpath_syntax.asp

### Exemples

* Select all the titles, as we don't suffix items with nothing to select all the "titre" node we need to write all its parents 
**items/item/titre**

* If we want to select a node by its name, whichever be its position in the document, we use //    
**//titre** 