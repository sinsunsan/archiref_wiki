### Links

* http://blog.coolaj86.com/articles/using-git-submodules.html   
* https://blogs.atlassian.com/2013/03/git-submodules-workflows-tips/   
* http://blogs.atlassian.com/2011/12/git-submodules

* This post explain how to use git submodule with an example. Tested work !   
http://vimcasts.org/episodes/synchronizing-plugins-with-git-submodules-and-pathogen/
* http://git-scm.com/book/en/Git-Tools-Submodules
* http://longair.net/blog/2010/06/02/git-submodules-explained   

**Alternatives to git submodules**    
https://blogs.atlassian.com/2013/05/alternatives-to-git-submodule-git-subtree/

###Clone a module with submodules

To download automatically submodules of a git repo 
You need to do 
* git submodule init 
* git submodule update 

The problem with this is that 
* the submodules are cheched out in a detached head state 
* there is no .git folder in the submodule but a .git file that reference a git folder inside the main repo 

when the following repo is itself in a repo, I have this error 
fatal: Not a git repository: /SEB/www/archiref/archiref_theme/.git/modules/compass/sass/ia_mix
fatal: 'git status --porcelain' failed in submodule default/themes/archiref_sky

It's due to the fact that I use to rsync my files to the server, and the local macbook path is saved in this files. 

The alternative, is to manually clone the sub repo, take more time but more secure. 