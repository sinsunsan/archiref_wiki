* **Send variables to the base template with extends**     
http://stackoverflow.com/questions/17244162/symfony2-twig-how-can-i-send-parameters-to-the-parent-template

`    {% set responsive = true %}`

need to be set in the template which extends another template. It could be placed at the top of the file, and it's scope will be valid in the entire file, even in the blocks. 
If you place it in a block it should be before the parent() called 
````
{% block before_wrapper %}
    {% set responsive = true %}
    {{ parent() }}
{% endblock %}`
````

* **How to define a wrapper block** 
Block that contain other blocks are allawed. However, to refine if (not using parent()) you need to put it in at least the definition of child block, because in this case, it's not automatically outputed.


```
{% block main %}
<div class="big-wrapper">
    {% block content %}
   My content
    {% endblock %}
</div>
{% endblock %}
```

```
{% block main %}
<div class="simple-wrapper">
    {% block content %}
    {{ parent() }}
    {% endblock %}
</div>
{% endblock %}
```

