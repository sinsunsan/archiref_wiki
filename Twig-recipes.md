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
