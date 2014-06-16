### use a variable to set an import url (only to import css file from an url)
````
$basePath: "../../../../../../app/Resources";
@import url("#{basePath)/sass/mixins/mysite/mysite_mixins.css")
````
http://sass-lang.com/documentation/file.SASS_REFERENCE.html#import

> Imports may contain #{} interpolation, but only with certain restrictions. It’s not possible to dynamically import a Sass file based on a variable; interpolation is only for CSS imports. As such, it only works with url() imports. For example:

> $family: unquote("Droid+Sans");
> @import url("http://fonts.googleapis.com/css?family=#{$family}");

***
### Compile a file manually (without grunt....) 

```
sass planning.scss --trace
```