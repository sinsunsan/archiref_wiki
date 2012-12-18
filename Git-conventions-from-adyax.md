h1. GIT conventions

{{toc}}

h2. Branching convention

There are 2 main branches that are ALWAYS present and used: *master* (contains major project releases and releases after each sprint) and *develop* (development code).
There are 3 supporting branches:
* feature branches - is created per each feature (task in redmine).
* release branches - is created after each sprint.
* hotfix branches - hot fixes in the master branch.

h2. Naming conventions for supporting branches

h3. Feature branch

* may branch only from *develop*
* must be merged back into *develop*
* must have next format _"[issue_id]-[name of the task]"_. There can be exceptional cases when there is not issue for the branch, in this case branch name must not start with _master_, _develop_, _release_, _hotfix_ and must have a good description explaining it's purpose.
* all commits in this branch must have format _"task #[issue_id]: description"_

h3. Release branch

* may branch only from *develop*
* must be merged into *develop* and *master*
* must have next format _"release-[release number]"_

h3. Hotfix branch

* may branch only from *master*
* must be merged into *master* and *develop*
* must have next format _"hotfix-[release number].[hotfix number]"_
* all commits in this branch must have format _"task #[issue_id]: description"_

h1. Workflow

h2. Get the code

h3. Clone the repository

<pre>
git clone git@web1.dev89.com:rue89v2 /path/to/repository/on/local/computer
</pre>

h3. Check branches

<pre>
git branch
</pre>

h3. Get latest changes from branch

<pre>
git co develop
git pull origin develop
</pre>


h2. Feature branch

h3. Create a feature branch

<pre>
git checkout -b 12345-test-issue develop
</pre>

h3. Merging finished feature with develop

<pre>
git checkout develop
git merge 12345-test-issue develop
git branch -d 12345-test-issue
git push origin develop
</pre>

h2. Release branch

h3. Creating release branch

<pre>
git checkout -b release-1.2 develop
</pre>

h3. Finishing a release branch

<pre>
git checkout master
git merge release-1.2
git tag -a 1.2
git push origin master
git checkout develop
git merge release-1.2
git push origin develop
git banch -d release-1.2
</pre>

h2. Hotfix

h3. Creating a hotfix

<pre>
git checkout -b hotfix-1.2.1 master
</pre>

h3. Finishing a hotfix

<pre>
git checkout master
git merge hotfix-1.2.1
git tag -a 1.2.1
git push origin master
git checkout develop
git merge hotfix-1.2.1
git banch -d hotfix-1.2.1
git push origin develop
</pre>