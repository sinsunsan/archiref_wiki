http://api.drupal.org/api/drupal/developer!topics!javascript_startup_guide.html/6#oop

* Use drupal behaviors instead of document.ready   
http://www.agileapproach.com/blog-entry/drupal-6-jquery-under-5-minutes

* All javascript function are attached to Drupal.behaviors object 
* php variables passed to javascript are stored in Drupal.settings
Drupal.settings are feeded in the php side by call to drupal_add_js
```
  drupal_add_js(array(
    'statusCheck' => array(
      'ajaxUrl' => url('system/ajax/rue89/user'),
      'type' => 'status',
      'progress' => '<img src="/' . $module_path . '/images/ajax-loader.gif" alt="" class="loading" /> ' . t('Search for availability'),
      'accepted' => t('Your situation appears next to your nickname'),
    ),
  ), 'setting');
```

* **The drupal object with it's method and sub objects**
```
Object
ahahError: function (xmlhttp, uri) {
attachBehaviors: function (context) {
behaviors: Object
checkPlain: function (str) {
encodeURIComponent: function (item, uri) {
formatPlural: function (count, singular, plural, args) {
freezeHeight: function () {
getSelection: function (element) {
jsEnabled: function getElementById() { [native code] }
locale: Object
parseJson: function (data) {
settings: Object
t: function (str, args) {
theme: function (func) {
themes: Object
unfreezeHeight: function () {
__proto__: Object
```



* **Start of misc/drupal.js**
```js
var Drupal = Drupal || { 'settings': {}, 'behaviors': {}, 'themes': {}, 'locale': {} };

/**
 * Set the variable that indicates if JavaScript behaviors should be applied
 */
Drupal.jsEnabled = document.getElementsByTagName && document.createElement && document.createTextNode && document.documentElement && document.getElementById;

/**
 * Attach all registered behaviors to a page element.
 *
 * Behaviors are event-triggered actions that attach to page elements, enhancing
 * default non-Javascript UIs. Behaviors are registered in the Drupal.behaviors
 * object as follows:
 * @code
 *    Drupal.behaviors.behaviorName = function () {
 *      ...
 *    };
 * @endcode
 *
 * Drupal.attachBehaviors is added below to the jQuery ready event and so
 * runs on initial page load. Developers implementing AHAH/AJAX in their
 * solutions should also call this function after new page content has been
 * loaded, feeding in an element to be processed, in order to attach all
 * behaviors to the new content.
 *
 * Behaviors should use a class in the form behaviorName-processed to ensure
 * the behavior is attached only once to a given element. (Doing so enables
 * the reprocessing of given elements, which may be needed on occasion despite
 * the ability to limit behavior attachment to a particular element.)
 *
 * @param context
 *   An element to attach behaviors to. If none is given, the document element
 *   is used.
 */
Drupal.attachBehaviors = function(context) {
  context = context || document;
  if (Drupal.jsEnabled) {
    // Execute all of them.
    jQuery.each(Drupal.behaviors, function() {
      this(context);
    });
  }
};
```

