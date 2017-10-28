# tpl()

The **tpl** ViewHelper returns an absolute URL inside the current templates folder. Should be used to create links to resources like images.

-> Since BIGACE 3.0

Further infos at the [ViewHelper tpl() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_Tpl.html).
    
## Attributes


*  **$url** - (optional, string)
    Returns either the URL to the given $url inside the public template folder OR (if $url === null) the ViewHelper itself.

## Example

This example shows how to adress an public template image:

	:::php
	  `<img src="<?php echo $this->`tpl('img/header.jpg'); ?>" alt="Logo" />

 

