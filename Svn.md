### Tuto
* **svn book** : A complete book in html on svn    
http://svnbook.red-bean.com/en/1.7/index.html
* http://www.tuteurs.ens.fr/logiciels/subversion/
* http://www.linuxfromscratch.org/blfs/edguide/chapter03.html#ch03-commit

* **svn download page**   http://apache.mirrors.tds.net/subversion/#sthash.k9LsBwzn.dpuf

### Commands
* **svn --version** : How to know the installed version of svn   
* **How to updated svn to a new version on mac**    
http://jason.pureconcepts.net/2012/10/updating-svn-mac-os-x/

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
* **Display the current svn:ignore value**   
````svn pg svn:ignore .````
