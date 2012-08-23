Les fonctions de preprocess peuvent être placer dans le template.php du theme.   
Ou dans un fichier theme.inc dans le module qui est responsable de template particulier.

Par exemple on peut avoir la structure :   
**site/all/module/monmodule/theme/theme.inc**


> For other functions, consider whether or not they really are needed at the presentation layer. If they are not, they can be used in the preprocessor layer. All templates may have an optional preprocess function, named template_preprocess_HOOK. For example, for our forums theme hook above, its preprocess function will be named template_preprocess_forums().

http://drupal.org/node/933976
