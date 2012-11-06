
* **Create a patch out of the difference with other branch**
<pre>
git format-patch master --stdout > fix_empty_poster.patch
</pre>

* **Create a patch out of a commit**   
```
git show HEAD > some-patch0001.patch
```   
Replace HEAD by a commit number 

http://ariejan.net/2009/10/26/how-to-create-and-apply-a-patch-with-git

* **Appliquer ce patch et autocommiter un commit du changement**
```
git am --signoff < fix_empty_poster.patch
```
