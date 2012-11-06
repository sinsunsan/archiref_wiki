* **Create a patch out of the difference with other branch**
<pre>
git format-patch master --stdout > fix_empty_poster.patch
</pre>

* **Create a patch out of a commit**   
<pre>
git show HEAD > some-patch0001.patch
</pre>
Replace HEAD by a commit number 
http://ariejan.net/2009/10/26/how-to-create-and-apply-a-patch-with-git

* **Appliquer ce patch et autocommiter un commit du changement**
<pre>
git am --signoff < fix_empty_poster.patch
</pre>

* **Revert a patch**   
http://drupal.org/patch/reverse
```
patch -p1 -R < path/file.patch
```
(If your patch was applied with the -p0 option, use that instead.)
Or:
```
git apply -R path/file.patch
```