### Make a checkox react when checking on another element 

The for attribute link the label element to the input element. 
So it suffice to click on one of these two element to make the checkbox "checked"
````
<div class="option checkbox">
   <input id="course-type1" name="main-choice">
   <label for="course-type1">
       <span class="text-label">Entrée</span>
   </label>
   <input id="course-type2" name="main-choice">
   <label for="course-type2">
       <span class="text-label">Entrée</span>
   </label>
</div>
````

* If you have several radios button which seem natural. Don't forget to add a name attribute which allow all radios button to be grouped together 
http://www.dummies.com/how-to/content/how-to-create-a-radio-button-in-an-html5-form.html

* If a form element with thes settings don't seem to work, check the id of the element. Indeed, per aps it's twice on a page. In this case only the first one will be valid.