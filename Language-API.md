## Misc

* How to force drupal language to be english (for debuging purpose)   

* Using hook_init and change global $language variable    
 http://deglos.com/blog/2010/06/12/overriding-language-drupal-backend

* **LANGUAGE_NONE**   
A elegant manner to refer to und   
http://api.drupal.org/api/drupal/includes%21bootstrap.inc/constant/LANGUAGE_NONE/7


## Pages

* [[t() function]]  
* [[Localization of taxonomy term]]
* [[Drupal 7 localization improvement]]
* [[content negociation]]
* [[change language in a page]]
* [[relationship of term language and node language]]

***

### General 
* When we change original string to be translated, the localization are lost. We need to do it again (d6 and 7)   


***

### Views

* Pour les champs custom markup, ne pas utiliser la valeur du champs, mais la valeur reecrite. La langue par défaut est toujours l'anglais pour les views (quel que soit la langue par défaut générale)

***

### User string translation 

18nstrings the module responsible for string translation
http://drupalcontrib.org/api/drupal/contributions%21i18n%21i18nstrings%21i18nstrings.module/6

Default language is translable !
http://drupalcontrib.org/api/drupal/contributions!i18n!i18nstrings!i18nstrings.module/function/i18nstrings_translate_langcode/6

***

### Modules that make translation in drupal 7
* locale -> module interface localisation    
http://drupal.org/documentation/modules/locale/
* i18n -> translation of the content (divided in 14 submodules)

***

### localization
* poedit is a external software that can more easily edit po translation file
http://www.poedit.net/download.php#linux