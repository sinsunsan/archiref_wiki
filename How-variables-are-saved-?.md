
This element value is saved automatically in variable table in the chartbeat_usenewsbeat variable
<pre>
 $form['chartbeat_usenewsbeat'] = array(
    '#type' => 'checkbox',
    '#title' => t('Use chartbeat publishing'),
    '#description' => t('<a href="@newsbeat">Chartbeat publishing</a> is a special edition of charbeat for journalists. ', array ('@newsbeat' =>'http://chartbeat.com/publishing')),
    '#default_value' => variable_get('chartbeat_usenewsbeat', ''),
  );
</pre>



If there is sub element the variable serialize an array 
<pre>
  $rue89_mailtemplates = variable_get('rue89_comments_mailtemplate', array());
</pre>

that could be accessed this way 
<pre>
'#default_value' => !empty($rue89_mailtemplates['template'][$i]['text']) ? $rue89_mailtemplates['template'][$i]['text'] : '',
</pre>
