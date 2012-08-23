When you want to change the language in a specific page manually and not set up whole drupal content négociation you can do it very easily

Language is a global variable so you can change this variable when you want depending of some conditions, as argument in the url. 

```
if (arg(0) == 'user' && arg(1) == 'register' && $_GET['lang'] == 'en' ){
      global $language;
      $language->language = 'en';
  }
```
When my url is is www.mysite.com/user/register?lang=en the language is et to english (if english has been set to use 'en' path prefix, though french is the default language and the content negotiation is set to off