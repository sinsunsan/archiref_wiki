* Use git merge or git rebase (in french) http://www.git-attitude.fr/2014/05/04/bien-utiliser-git-merge-et-rebase

* A git merge must be in one commit only !

* How to tell git what to do with the file 
Fix the conflict manually and write git add theFile of git rm theFile to say ok or nok

* Binary merge conflict 
http://lostechies.com/joshuaflanagan/2010/01/29/how-to-resolve-a-binary-file-conflict-with-git/

* Merge conflict types 
http://nvie.com/posts/a-successful-git-branching-model/
`git merge --no-ff release-1.2`

* Find both version in the tree
```find . -name _navbar.scss```
May be very useful to find duplicate files both maintained in the tree by git

### How to merge files that has been splitted 

http://stackoverflow.com/questions/2953808/merge-changes-when-a-file-on-a-branch-has-split-into-two-files-on-the-master

### Merge technics 

#### Manual merge 
When a file is being splitted for example, 
the automatic merge is very complicated to undesrtand 
One technics is : 

* Use the last version of the file from the branch where we want to merge something 
* use git diff commit commmit afile to get a diff of all changes in the problematic file 
* in the diff use context to identify the insertion points 
* copy and paste the code modification one by one


### Show the changes separately 

http://stackoverflow.com/questions/101752/aborting-a-merge-in-git#107860
````
# common base:
git show :1:_widget.html.erb

# 'ours'
git show :2:_widget.html.erb

# 'theirs'
git show :3:_widget.html.erb
````

We can use git diff
````
git diff :2:file.txt :3:file.txt
````

### Use 3 style 
http://stackoverflow.com/questions/16990657/git-merge-diff3-style-need-explanation
Indicate HEAD / the merged branch / and the common base