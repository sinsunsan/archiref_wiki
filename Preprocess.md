* **Setting up variables for use in a template (preprocess and process functions)**   
http://drupal.org/node/223430


* **View Preprocess view for drupal 6**      
http://evolvingweb.ca/story/theming-views-drupal-templates-and-preprocess-functions

* **example of preprocess naming convention**   
Formula  : moduleName_preprofunction rue89_platform_users_preprocess_rue89_activity(&$vars)cess_hook   
**Name of the function** :function rue89_platform_users_preprocess_rue89_activity(&$vars)   
**Name of the module** : rue89_platform_users   
**Name of the template in which the preproccessed variables are available** : 
rue89-activity-article.tpl.php   


### View proprocess drupal 7
Preprocess has changed for drupal 7
For view preprocessing, it has special issue describe in this post 
http://webpartners.es/en/drupal-7-views-templates-and-preprocess?utm_source=twitterfeed&utm_medium=twitter
Here is a code to make the    
https://gist.github.com/c094d624442fa44a58a4



Les fonctions de preprocess peuvent être placer dans le template.php du theme.   
Ou dans un fichier theme.inc dans le module qui est responsable de template particulier.

Par exemple on peut avoir la structure :   
**site/all/module/monmodule/theme/theme.inc**


> For other functions, consider whether or not they really are needed at the presentation layer. If they are not, they can be used in the preprocessor layer. All templates may have an optional preprocess function, named template_preprocess_HOOK. For example, for our forums theme hook above, its preprocess function will be named template_preprocess_forums().

http://drupal.org/node/933976