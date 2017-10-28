# filename()

The **filename** ViewHelper strips the Bigace root directory from an absolute filename. This is useful to prevent information disclosure. Just pass a filename (like a log stacktrace) and you can be sure that no path information are leaked.

-> Since BIGACE 3.0

Further infos at the [ViewHelper filename() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_Filename.html).

## Attributes


*  **$url** - (__required__, string)
    The $url is the (absolute) filename that should be cleaned.
 

## Example

This example assumes that Bigace is installed in "/var/www/bigace/":

	:::php
	<?php
	
	  echo "Filename: " . $this->filename('/var/www/bigace/library/Bigace/Bigace_Hooks.php');
	
	?>


would result in the output:

	
	Filename: library/Bigace/Bigace_Hooks.php


