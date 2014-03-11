http://twig.sensiolabs.org/

* Syntax {{}} as in [[handlebars]]
* Conditional structure to iterate on an array 
````
{% for user in users %}
    * {{ user.name }}
{% else %}
    No users have been found.
{% endfor %}
````
