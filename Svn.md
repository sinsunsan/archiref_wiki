### Tuto
* **svn book** : A complete book in html on svn    
http://svnbook.red-bean.com/en/1.7/index.html

* http://www.tuteurs.ens.fr/logiciels/subversion/


### Commands
* **svn diff** : Show the diff between two revisions   

Display the diff between current state of files and revision r72
```
/var/www/cemaforre2$ svn diff --revision r72
```

* **svn checkout** : Checkout to a difference branch or revision ?
* **svn status** : Status of the current svn tree (clean or dirty == git status)
* **svn commit** : Commit the change and send it to the server (no git push needed)

* **Ignore files**
http://svnbook.red-bean.com/en/1.7/svn.advanced.props.special.ignore.html   
````svn propset svn:ignore dirname .````



