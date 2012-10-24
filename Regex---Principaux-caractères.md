<pre>
^ Le début de la chaîne (à mettre avant la chaîne à repérer)
$ La fin de chaîne (à mettre après la chaîne à repérer)
# Quelque part dans la chaîne 
| Ou 
</pre>

### Les plages de caractères
<pre>
[^/] pas un slash ( à noter que ^ veut dire n'est pas dans ce contexte(à l'intérieur de crochet)
[amli] Un caractère qui soit a ou m ou l ou i
[^0-9] Pas un chiffre
[a-z] Une lettre de a à z en minuscule
.     Tout- n'importe quel caractère
(.+) N'importe quel caractère 1 x ou plus (englobé par une parenthèse capturante)
</pre>

### Les classes abrégées 

<pre>
\d	Indique un chiffre. Ça revient exactement à taper [0-9]
\D	Indique ce qui n'est PAS un chiffre. Ca revient à taper [^0-9]
\w	Indique un caractère alphanumérique ou un tiret de soulignement. Cela correspond à [a-zA-Z0-9_]
Comprend également les accents
\W	Indique ce qui n'est PAS un mot. Si vous avez suivi, ça revient à taper [^a-zA-Z0-9_]
\s	A single whitespace character
ùûüÿàâæçêéèëïîôœ   French accent Other language accents here http://french.typeit.org/
</pre>


### Les quantificateurs
Se place aprés la symbole ou plage qu'elle quantifie.   
Par exemple :    
[a-z]* Autant de letttre de a à z qu'on veut   
p? 0 ou 1 p    
<pre>
? 0 ou 1 fois
+ 1 ou plusieurs fois 
* 0 1 ou plusieurs fois
{3} 3 fois excatement
{3,} au moin 3 fois
{5,8} de 5 à 8 fois
</pre>