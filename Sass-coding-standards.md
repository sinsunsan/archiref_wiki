### Comments
* Big separation insivible in output
```
This style is doxygen style, note very visible in the style sheet, 
but recognized by text editors and doxygen export of course.
/**
 * Blog Article page
*/
```

* Small annotation on a selector
```
// Le formulaire de modification d'un node de type archiref image
.page-archiref-image.page-node-edit select {
  width: 200px;
}
```

## Files organization
### Drupal specific

Insert all files in one so make a scss files that serve as an importer 
And name and imported files prefixed with _ so that they are not outputed as sperated file

* HTML : General html settings
* Layout : General layout 

* Node display : Full node display
* Node edit form
* View display
* Page : Specific pages like contact page, about page...
* Home : Homepage

## rules organization in a files 


* Start with a "general" section that group all rules that are not page specific
* Make a divider comment between each following section, and wrapped page specific rules

