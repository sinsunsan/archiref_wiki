http://twig.sensiolabs.org/

### why use it as a php developer 

* Reduce php verbosity 
* easy to learn and less error prone by comparison with plain php 

### Main features 

* Syntax {{}} as in [[handlebars]]
* Conditional structure to iterate on an array 
````
{% for user in users %}
    * {{ user.name }}
{% else %}
    No users have been found.
{% endfor %}
````
* multiple inheritance, blocks, automatic output-escaping
