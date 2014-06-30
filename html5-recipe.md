### Make a checkox react when checking on another elemnt 

The for attribute link the label element to the input element. 
So it suffice to click on one of those to make the checkbox checked
````
<div class="option checkbox">
   <input id="course-type1">
   <label for="course-type1">
       <span class="text-label">Entrée</span>
   </label>
</div>
````

Don't forget to add a name attribute which allow all radios button to be grouped together 
http://www.dummies.com/how-to/content/how-to-create-a-radio-button-in-an-html5-form.html