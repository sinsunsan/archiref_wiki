Content negociation is the way a site choose the language in which to display the language 
In drupal 6
> Préfixe de chemin avec solution dégradée. La langue de présentation sera déterminée par la recherche dans le chemin d'accès d'un code de langue ou d'une chaine personnalisée identique à cette spécifiée dans le "Prefixe de chemin" de chaque langue. Si aucun préfixe n'est identifié, la langue d'affichage est déterminée par les préférences réglées par l'utilisateur dans sa page Mon compte, ou par les réglages de son navigateur. Si aucune langue ne peut être déterminée, la langue par défaut sera utilisée.

Donc 
si en/node/222
- si en est présent, ce sera toujours l'anglais 
- si l'utilisateur est connecté, ce sera sa langue de préférence (si elle est reglé)
- sinon la langue du navigateur c'est à dire le header http de langue

Il existe une extension firefox pour forcer les paramètres de langues envoyés 
https://addons.mozilla.org/en-US/firefox/addon/quick-locale-switcher/

On peut ainsi voir la version qui est proposé quand les utilisateurs sont à l'étranger. 

###Langue et path auto

Si un contenu est en français, et que la langue de fallback est l'anglais
Si ce contenu à un pattern de renommage avec path auto en français, alors en anglais on verra le contenu 
mais le chemin sera le chemin machine
en/node/754 si le node 754 n'est pas traduit, si il est traduit on a /en/my_tranlated_content qui est le chemin renomé du node 947 la traduction anglaise du node 754
