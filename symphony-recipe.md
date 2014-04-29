* Customize a form with custom attributes 

````    {{ form_widget(form.recipeName, { 'attr': { 'class': 'search-query', 'placeholder': 'Rechercher dans les recettes' , 'ng-model': 'search.q'}, 'required': false}) }}````
