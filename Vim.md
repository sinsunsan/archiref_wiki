###  Ressources

Cheatsheet for vim     
http://www.pixelbeat.org/vim.tips.html   
http://www.worldtimzone.com/res/vi.html

Screencast on vim    
http://vimcasts.org/

Configuration de vim   
https://github.com/astrails/dotvim/blob/master/README.markdown

* **Numéros de ligne** 

Voir les numéros de ligne 
*:set number*

Ne plus voir les numéros de ligne 
*:set nonumber*

* **Décaler une section**

"
   > indent   
   < unindent
"


Pour décaler toute une section 
Faire v pour selection une grand portion de texte
puis :> par exemple pour décaler d'une tab

* **Code folding in vim**
http://smartic.us/2009/04/06/code-folding-in-vim/
<pre>
:help folding Detailed help about folding
The following commands are without :
za toggle folding (locally)
zM Fold everything 
zR Unfold everything
zm Fold locally
zr Unfold locally
</pre>
[[Vim fold commands list]]

* **search and replace in vim**
This line will search and replace in all the current document    
 :%s/texte_à_trouver/nouveau_texte/g 

* **copy all, cut all**   
```
// Go to the beggining of the file
gg
// Yank = copy (y) till the end of the file (G) 
yG
// Or cut (d) till the end of the file
dG
```
* **code indenting bug > Automatic identation**   
There is sometimes a identing bug when copying code from editors. 
It happen to me with .sh files, try to create the file without extension, and to rename it after. 

Solved: it's due to a special mode in vim, there is two modes :no paste the normal mode and :set paste the special mode. In normal mode vim try to preserve the correct indentation and it get lost. In this mode, use the visual mode with v and type = to reindent correctly. 

To have the original identation of the chunk being paste type :set paste


* **Install vim extension**

How to install   
http://stackoverflow.com/questions/1639606/how-do-i-install-a-plugin-for-vim

SASS SCSS Syntax
https://github.com/tpope/vim-haml

Markdown syntax
http://plasticboy.com/dox/vim-markdown.zip