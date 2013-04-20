Load newer css always
http://css-tricks.com/snippets/wordpress/prevent-css-caching/

```
<link rel="stylesheet" href="<?php bloginfo('stylesheet_url'); echo '?' . filemtime( get_stylesheet_directory() . '/style.css'); ?>" type="text/css" media="screen" />
```