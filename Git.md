### Pages 

* [[Git debug]]   
* [[Git howto]]    
* [[Git recipes]]   
* [[Git config]]   
* [[Git submodules]]   
* [[git housekeeping]]
* [[Git merge]]
* [[git best pratice]] / standard commit message, what to do, what not to do
* [[Git hook]] / Trigger something when a git action happen

**Drupal and Git best practices**   
https://drupal.org/node/803746

### Liens 

Référence de Adyax    
http://nvie.com/posts/a-successful-git-branching-model/
http://vimcasts.org/episodes/synchronizing-plugins-with-git-submodules-and-pathogen/

### Git 

* **[[Git Patch]] Manage patch with git** 
* **[[Git Log]] Browse git history**

**Branch, checkout**   

### Create a feature branch (and track the original branch)
Le premier argument est le nom de la banch, le deuxième la branch où l'on se branche
L'option track permet de rester synchroniser avec les changements qui ont lieu dans la branche d'origine
<pre>
git checkout --track -b 12345-test-issue develop
</pre>


### [[git diff]] // reveal differences between revision   

### Retrouver la version d'un fichier tel qu'il était au dernier commit (quand on a des changements non commités)
<pre>
git checkout rue89-page-header-autopromo.tpl.php
</pre>

* **List all files that are under version control**    
````git ls-tree -r 1.3 --name-only````


### Filtrer ses commits de la liste des commits
<pre>
git log | grep Lucas -A 3 -B 1
</pre>

-A les lignes au dessus
-B les lignes en dessous


### Merger dans master si on ne l'avait pas tracké au départ
<pre>
git merge origin/master
</pre>

### Connaître toutes différences de sa branche avec une autre branche
<pre>
git diff origin/master
</pre>
Pas la peine de spécifier deux branches, la courantes est sélectionnée par défaut

### Faire du nettoyage avec git pour supprimer tous les changements qui ne sont pas intentionnels

* Se mettre sur la branche que l'on veut nettoyer
* Faire un git diff origin/master pour connaitre les différences
* faire un git checkout origin/master lefichier où l'on veut enlever tout changement
* Faire un git diff origin/maser pour voir ce que l'on a nettoyer ou on en est en fait


### Voir l'état du code dans une branch ou un commit sans changer l'état courant 

Shows the contents of the file Documentation/README as they were current in the 10th last commit of the branch next.
<pre>
http://www.kernel.org/pub/software/scm/git/docs/git-show.html
git show next~10:Documentation/README
</pre>

### Créer des alias pour git 

<pre>
#make "com" alias for "commit"
git config alias.com commit

#make "co" alias for checkout
git config alias.co checkout

#make "br" alias for branch
git config alias.br branch
</pre>

* **Restore a given commit**   
```git reset --hard 7208c2f3c30d0ca9f5456fad0bd0701fc2cf6fad```

Will restore the state of file as it was at this commit. 


### Remove a commit in a remote repository( like github)

```git push -f origin HEAD^:master```

### Restore a file on another branch : We pipe the result of  git show

```
git show master:files.php > files.php
```