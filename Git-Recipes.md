### **Update files being ignored after updating a .gitignore file**   
When you update the gitignore, the files already in the index but matching the gitignore don't get updated.   
To force the update 

http://stackoverflow.com/questions/1139762/gitignore-file-not-ignoring

```
git rm -r --cached .
This removes everything from the index, then just run:

git add .
Commit it:

git commit -m ".gitignore is now working"
```

### **Delete files untracked files**   
```
git clean -f
``` 
Will delete all files present in the directory but not tracked in the git repo. 
Git stash can't work in that case, as the files are not tracked, no it's not local changes. 

http://stackoverflow.com/questions/61212/removing-untracked-files-from-your-git-working-copy

To clean files and directory  (Useful in most cases)   
```
git clean -f -d
```

### Quit a merge process without merging 

If you want let's say only see all the merge conflict without merging anything. 
To get back to your unmerge branche state, you have a command option --abort
````
git merge --abort 
git cherry-pick --abort
````


### Reset hard even if there is untracked file 

When doing a merge, we sometime need to do a ```git reset --hard``` instead of a git merge --abort 
But there is often some untracked files, due to the merge. 
If you do ```git reset --hard```, it will not remove the untracked files. 

To solve this it's very easy ! 
Add the untracked files 

```git add --all``` 


### have a word by word diff 
The both modified lines show both version on the same line, with different colors.
````
git diff --word-diff=color 0364798 565d44b  myfile.css
````
