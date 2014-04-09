### Cool features

* When selecting a word, if the word is present elsewhere in the file, it's visually identified by a border.
Useful when you want to quickly identify where a variable or a function is being used.


### Recipe 

* **Search a file or a line number**   
Cmd + P allow to search a file or go to a line number   
To switch between 2 modes, type :873 to go to line 873    
Else start typing and the search will display files names that match

* **Exclude a folder(s) from search**   
To exclude cache and log from a symphony environnement
````
,-/Users/sebastien/sshfs/sf/dev/myproject/app/cache*, -/Users/sebastien/sshfs/sf/dev/myproject/app/logs/dev.log
````
Don't forget the , at the beginning
