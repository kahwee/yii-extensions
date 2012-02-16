KRichTextEditor
===============

KRichTextEditor generates a rich text editor interface using tiny mce.

An example usage would be:

```
Yii::import('ext.krichtexteditor.KRichTextEditor');
$this->widget('KRichTextEditor', array(
  'model' => $model,
	'value' => $model->isNewRecord ? $model->{$name} : '',
	'attribute' => $name,
	'options' => array(
		'theme_advanced_resizing' => 'true',
		'theme_advanced_statusbar_location' => 'bottom',
	),
));
```

Assigning options would overwrite the default options that will be passed to tiny mce jquery plugin.

Default options
---------------

```
public $defaultOptions = array(
  'theme' => 'advanced',
	'theme_advanced_toolbar_location' => 'top',
	'theme_advanced_toolbar_align' => 'left',
	'theme_advanced_buttons1' => "bold,italic,underline,strikethrough,|,fontselect,fontsizeselect",
	'theme_advanced_buttons2' => "bullist,numlist,|,outdent,indent,blockquote,|,undo,redo,|,link,unlink,image,cleanup,code,|,forecolor,backcolor",
	'theme_advanced_buttons3' => '',
);
```

More information
----------------
 
 * [TinyMce jQuery plugin example](http://www.tinymce.com/tryit/jquery_plugin.php)
 * 