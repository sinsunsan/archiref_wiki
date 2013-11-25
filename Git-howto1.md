* **Update files being ignored after updating a .gitignore file**   
When you update the gitignore, the files already in the index but matching the gitignore don't get updated.   
To force the update 

http://stackoverflow.com/questions/1139762/gitignore-file-not-ignoring

````
git rm -r --cached .
This removes everything from the index, then just run:

git add .
Commit it:

git commit -m ".gitignore is now working"
````