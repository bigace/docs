# dojo()

The **dojo** ViewHelper was implemented to make sure, that we use a pre-configured system. It extends the Zend implementation only in that kind, that the path information is correct, Bigace specific locale and theme are used.

Read more about the [Dojo Javascript Framework](http://www.dojotoolkit.org/).

If you want to use the dojo ViewHelper, refer to the Zend [documentation](http://framework.zend.com/manual/en/zend.dojo.view.html) and [API](http://framework.zend.com/apidoc/core/) (Package: Zend_Dojo_View_Helper).

-> Since BIGACE 3.0

Further infos at the [ViewHelper dojo() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_Dojo.html).

## Example

This example shows how to activate Dojo in your layout.

	:::php
	<?php
	
	  $this->dojo();
	
	?>


