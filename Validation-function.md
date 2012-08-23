La fonction de validation par défaut est form_id_validate 
D'autre part son nom est visible dans la clef $form['#validate']

Bon exemple
<pre>
<code class="php">
**
 * Implementation of hook_form_alter().
 */function my_module_form_alter(&$form, $form_state, $form_id)  {
 if ($form_id == 'user_profile_form') {
  array_unshift($form['#validate'], 'email_check_validate');
 }
}
 
/**
 * Validate profile form
 * Force form error if new email address matches current email address
 *
 */
function email_check_validate ($form, $form_state)  {
  global $user;
  $old_email = $user->mail;
  $new_email = $form_state['values']['mail'];
 
  if ($old_email ==  $new_email) {
    form_set_error('mail', t('Your email could not be changed'));
  }
}
</code>
</pre>   
