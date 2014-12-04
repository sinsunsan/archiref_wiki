# Tools

{{>toc}}

http://gitk.sourceforge.net/
http://www.git-legit.org/

# Create a local branch

## Create a branch

Create a feature branch (and track the original branch)
<pre>
git checkout --track -b 12345-test-issue develop
</pre>

## Output a diff of the branch

While in the branch:

<pre>
git diff develop..HEAD
git diff --name-status develop..HEAD
git diff --stat --color develop..HEAD
</pre>


## Combine our commits into one

First check the status, remember how many commits we have done (3)
<pre>
git status
# On branch 99999-foo
# Your branch is ahead of 'develop' by 3 commits.
nothing to commit (working directory clean)
</pre>

Display the log for these 3 commits
<pre>
git log --pretty=oneline -3
</pre>

Combine our 3 commits into one. when into the editor, leave the first one as 'pick', and set the following ones as 'squash'. then, in the next editor, replace the commit messages with a new one
<pre>
git rebase -i HEAD~3
</pre>

Extract our commit as a patch
<pre>
git format-patch 
</pre>

## Change commit message

On last commit:
<pre>
git commit --amend -m "task #99999: foo bar"
</pre>

## Pushing our branch

Merging finished feature with _develop_
<pre>
git checkout develop
git merge 12345-test-issue
git branch -d 12345-test-issue
git push origin develop
</pre>

## Keep in sync

Pulling new changes from _develop_ branch, into our working branch
<pre>
git fetch origin       
git merge origin/develop  
</pre>


## Rebase

Move our branching to start from the latest _develop_
<pre>
git rebase develop
</pre>

Eventually, fix conflicts, and then _git add_ the modified files, and then continue the _rebase_
<pre>
git add a/b/c/foo
git rebase --continue
</pre>

A _git status_ will show:
<pre>
Your branch and 'origin/12345-test-issue' have diverged,                      
and have 531 and 150 different commit(s) each, respectively.
</pre>

Do a _git pull_, it may show conflicts
<pre>
git pull                                               
Auto-merging a/b/c/foo                         
CONFLICT (content): Merge conflict in a/b/c/foo                             
Automatic merge failed; fix conflicts and then commit the result.  
</pre>

So fix the conflicts, _git add_ the files, and then commit the fix
<pre>
git add a/b/c/foo
git commit -a -m 'solved conflicts'
</pre>

If everything is fine, then push the branch to remote
<pre>
git push origin 12345-test-issue
</pre>

# Share our local branch with others

You have a local branch, but you want to save it on remote so that others can work on it. So there is _you_ and _other_.


## Push our branch to remote

_Do this on_ your _machine_

list branches , and checkout our feature branch
<pre>
git branch     
git checkout 123456-foobar
</pre>

Push branch to origin
<pre>
git push origin 123456-foobar  
</pre>

## Other dev checkouts our branch

_Do this on the_ other _machine_

Update local repository and list remote branches
<pre>
git fetch origin
git branch -r
</pre>

Checkout and track feature branch
<pre>
git checkout --track origin/123456-foobar
</pre>

Do a change, and commit, and push on remote feature branch
<pre>
git commit -a -m 'test commit to remote branch'
git push origin 123456-foobar
</pre>


## Track our new remote branch 

_Do this on_ your _machine_

delete local branch, we will fetch the remote instead
<pre>
git branch -D 123456-foobar
</pre>

Make sure everything is up to date, and list remote branches
<pre>
git fetch origin
git branch -r
</pre>

Check out and track the remote feature branch into a local branch
<pre>
git checkout  --track origin/123456-foobar && git pull
</pre>

Or, if you want to get the remote branch into a different local branch
<pre>
git checkout  --track -b foo origin/123456-foobar && git pull
</pre>

Then it is as when you had just a local branch. You can commit, push, etc...

##  Delete remote branch

<pre>
git push origin :123456-foobar
</pre>

It is still shows up locally...

<pre>
git push origin :refs/heads/release
</pre>

And to remote tracking branches in local repositories

<pre>
git remote prune origin
</pre>

## h2. Links

http://www.mariopareja.com/blog/archive/2010/01/11/how-to-push-a-new-local-branch-to-a-remote.aspx
http://www.zorched.net/2008/04/14/start-a-new-branch-on-your-remote-git-repository/


# Checkout and track a branch

<pre>
git checkout --track -b release origin/release
</pre>



##  How to reapply a commit

For instance, if a feature has been changed in code before it was dumped on prod, we need to:
* dump the feature on prod into a tar.gz
* untar the feature into our tree
* commit the changes
* we now have in the code the synced feature (git code = prod DB)
* apply the old commit which was done before the feature is dumped (see below)
* check if the changes match the old commit
* commit the changes
* on our local instance, dump the feature again, and add it into the code
* check that the diff is only trivial (spaces...), and commit again
* now we have a dumped feature in code which matches the prod DB + the old commit

In order to re-apply the old commit, do:
* in _gitk_, click on the old commit
* right click, and choose _Write commit to file_
* in the field _Command_, add _-w_ (to ignore whitespace)
* click _Write_ (it should write in /var/www/rue89v2/dev/)
* then go to /var/www/rue89v2/dev/ where the patch is
* do _patch -p1 < commit-xxxxxx_ to apply the patch
* check with _git diff_ that the changes match the old commit


#  Compare two versions of a same file

Compare a file across to pushed branches
<pre>
git diff origin/develop origin/release-20111221 -- sa/b/c/foo.bar
</pre>

#  Delete a remote tag

<pre>
git tag -d 12345
git push origin :refs/tags/12345
</pre>

If a new tag doesn't appear when you do a _git fetch origin_, you can try:
<pre>
git pull --tags
</pre>

#  Cancel a commit

If you have done one commit (and haven't pushed it yet), you can cancel it

This will set HEAD to the previous commit, delete the previous commit, and set you files to match the new HEAD:
<pre>
git reset --hard HEAD~1
</pre>


But this one will set HEAD to the previous commit, delete the previous commit, but leave your files as is, which allows to you to do a few changes to what you commited wrongly, and re-commit:
<pre>
git reset HEAD~1
</pre>

If you cancel several commits, but you have pushed some to origin, you can (to check!):

Push it to origin, using _--force_ to force the new HEAD position
<pre>
git push --force origin foo
</pre>

Then, on other instances/machines, you may have to delete the branch and get it again, in order to be at the right HEAD:
<pre>
git br -D foo
git checkout --track origin/foo
</pre>

#  Cancel a pushed merge

If you have merged something into your branch, and then pushed it, but realized later that the merge was wrong, you can undo it like this:

First, find the commit (or tag) prior to the merge, using _git log_, and reset your local copy to it:

<pre>
git reset --hard b898e29dc0fe12523716293c25d9a7201619cc34
git reset --hard 2.2.0-56
</pre>

Then, push it to origin, using _--force_ to force the new HEAD position
<pre>
git push --force origin master
</pre>

Then, on other instances/machines, you may have to delete the branch and get it again, in order to be at the right HEAD:
<pre>
git br -D master
git checkout --track origin/master
</pre>


#  Display current branch in bash prompt

Add this in the .bashrc

<pre>
c_red=`tput setaf 1`
c_green=`tput setaf 2`
c_sgr0=`tput sgr0`

parse_git_branch () {
  if git rev-parse --git-dir >/dev/null 2>&1
  then
    gitver=$(git branch 2>/dev/null| sed -n '/^\*/s/^\* //p')
    if git diff --quiet 2>/dev/null >&2
    then
      gitver=${c_green}' ['$gitver']'${c_sgr0}
    else
      gitver=${c_red}' !['$gitver']'${c_sgr0}
    fi
  else
    return 0
  fi
  echo $gitver
}
</pre>

Then, in the prompt, add this _\$(parse_git_branch)_, so it looks for instance like this:

<pre>
PS1="${debian_chroot:+($debian_chroot)}:\[\033[00;36m\]\w\[\033[00m\]\$(parse_git_branch)\$ "
</pre>


### Search with git grep

Very fast search 

Search the string "mobileMenu" with line numbers and output it in less (so Q to quit) 
<pre>
git grep -n -a mobileMenu
<pre>

For only html.twig files
<pre>
git grep -n -a "page-wrapper closed" -- '*.html.twig' 
<pre>
