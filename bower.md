### Installation 

```
#!bash
npm install -g bower #Install bower with npm globally (available in every folder)
```

#### Useful commands
```
#!bash
bower list #List all installed package 
bower install #Install the dependencies listed in bower.json
bower update #update installed dependencies
bower search packageName #Search a package name 
bower info packageName # with an exact package name, get info (read the bower.json and get available versions)
```

* **Update only one library** 
bower update will always update all libraries that need to. 
To update only one library use bower install instead. 
It will override, the previous version 


### Bower versioning 

Bower use versionning syntax used in [[SEMVER]] that stand as semantic versionning


#### Tutorials 

* http://www.synbioz.com/blog/bower   
* http://blog.teamtreehouse.com/getting-started-bower
* http://code.tutsplus.com/tutorials/meet-bower-a-package-manager-for-the-web--net-27774


#### Bower recipes 

How to download only useful files with bower 
http://joshbranchaud.com/blog/2014/02/19/Managing-Single-Files-With-Bower.html