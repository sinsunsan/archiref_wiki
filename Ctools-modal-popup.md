```
/**
 * @file
 * Implement a modal form using AJAX.
 *
 * The modal form is implemented primarily from mc.js; this contains the
 * Drupal specific stuff to use it. The modal is fairly generic and can
 * be activated mostly by setting up the right classes, but if you are
 * using the modal you must include links to the images in settings,
 * because the javascript does not inherently know where the images are
 * at.
 *
 * You can accomplish this with this PHP code:
 * @code {
 *   ctools_include('modal');
 *   ctools_modal_add_js();
 * }
 *
 * You can have links and buttons bound to use the modal by adding the
 * class ctools-use-modal.
 *
 * For links, the href of the link will be the destination, with any
 * appearance of /nojs/ converted to /ajax/.
 *
 * For submit buttons, however, the URL is found a different, slightly
 * more complex way. The ID of the item is taken and -url is appended to
 * it to derive a class name. Then, all form elements that contain that
 * class name are founded and their values put together to form a
 * URL.
 *
 * For example, let's say you have an 'add' button, and it has a select
 * form item that tells your system what widget it is adding. If the id
 * of the add button is edit-add, you would place a hidden input with
 * the base of your URL in the form and give it a class of 'edit-add-url'.
 * You would then add 'edit-add-url' as a class to the select widget
 * allowing you to convert this value to the form without posting.
 *
 * If no URL is found, the action of the form will be used and the entire
 * form posted to it.
 */
```
