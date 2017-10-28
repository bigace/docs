# content()

Returns the named content for the current or given item.

-> Since BIGACE 3.0

Further infos at the [ViewHelper content() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_Content.html).

## Attributes


*  **$name** - (optional, string)
    The name of the content, as described in [Zend_Layout (meta information)](../zendtemplate#meta_information). If not given, the default content is used.

*  **$item** - (optional, Item)
    The item to fetch the content for. If not given, the current page is used.

## Example 1

This example shows how to output the default content of the current page.

	:::php
	<?php
	
	  $foo = $this->content();
	
	?>

## Example 2

This example shows how to output the content 'contact' of the current page.

The Layout definiton:

	:::php
	<?php
	/*
	Description: An example layout
	Contents: contact

	*/
	?>


	:::php
	<?php
	
	  $foo = $this->content('contact');
	
	?>


