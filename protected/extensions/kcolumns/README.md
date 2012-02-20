KHtmlPurifierColumn
===================

KHtmlPurifierColumn represents a grid view column that renders purified html in each of its data cells. It also does truncation when specified.

KHtmlPurifierColumn removes all malicious code (better known as XSS) with a thoroughly audited, secure yet permissive whitelist. It will also make sure the resulting code is standard-compliant.

It uses CHtmlPurifier which is wrapper of [HTML Purifier](http://htmlpurifier.org).

CHtmlPurifer is provided as part of Yii Framework.

KHtmlPurifierColumn accepts options from [HTML Purifier](http://htmlpurifier.org/live/configdoc/plain.html).

Usage as part of column in `CGridView`:

```php
<?php
$this->widget('zii.widgets.grid.CGridView', array(
	'dataProvider' => $model->search(),
	'columns' => array(
		array(
			'class' => 'ext.kcolumns.KHtmlPurifierColumn',
			'name' => 'content',
			'options' => array(
				'HTML.AllowedElements' => array('i', 'em', 'strong', 'b', 'sup', 'sub'),
				'HTML.AllowedAttributes' => array(),
			),
			'truncate_length' => 200, #Number of characters limit for truncation.
			'truncate_suffix' => '&hellip;', #Ellipses
		),
		array(
			'name' => 'id',
		),
	),
));
```

In the above example, `HTML.AllowedElements` is one of the many configuration
options of [HTML Purifier](http://htmlpurifier.org/live/configdoc/plain.html).

More information
----------------

 * [HTML Purifier](http://htmlpurifier.org/live/configdoc/plain.html)
 * [GitHub](https://github.com/kahwee/yii-extensions/tree/master/protected/extensions/kcolumns)
