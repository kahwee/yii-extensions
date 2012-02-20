KColumns
========

I plan to clean up and open source more of my Yii extensions. Please be patient. :)

KHtmlPurifierColumn
-------------------

KHtmlPurifierColumn represents a grid view column that renders purified html in each of its data cells. It also does truncation when specified.

It uses CHtmlPurifier, provided as part of Yii Framework, which is wrapper of [HTML Purifier](http://htmlpurifier.org). HTML Purifier removes all malicious code (better known as XSS) with a thoroughly audited, secure yet permissive whitelist. It will also make sure the resulting code is standard-compliant.

KHtmlPurifierColumn accepts options from [HTML Purifier](http://htmlpurifier.org/live/configdoc/plain.html).

Usage with in `CGridView` as a column class:

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
			'truncate_length' => 250, #Number of characters limit for truncation.
			'truncate_suffix' => '&hellip;', #Ellipses
		),
		array(
			'name' => 'id',
		),
	),
));
```

In the above example, `HTML.AllowedElements` is one of the many configuration options of [HTML Purifier](http://htmlpurifier.org/live/configdoc/plain.html). Specifying a `truncate_length` of 250 truncates the content within 250 characters. It also removes all links and `style` attributes in HTML elements.

Page output
-----------
This is an example of what the browser can render using the above example:

![Screenshot of KHtmlPurifierColumn](https://github.com/kahwee/yii-extensions/raw/master/protected/extensions/kcolumns/KHtmlPurifierColumn-screenshot.png "Screenshot of KHtmlPurifierColumn")

More information
----------------

 * [HTML Purifier configuration options](http://htmlpurifier.org/live/configdoc/plain.html)
 * [GitHub](https://github.com/kahwee/yii-extensions/tree/master/protected/extensions/kcolumns)
