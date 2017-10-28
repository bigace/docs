# fileMerge()

The **fileMerge** ViewHelper compresses and combines CSS and Javascript files.

To speed up your website, its important to reduce the amount of webserver requests. The benefit of this tag is to combine the files for you on the fly, so you can still work on multiple CSS files, while the user gets only one large CSS file.

As it cuts out comments, new lines and whitespaces, you don't have to care about minified versions of the files - they will be automatically stripped out for the productive CSS files.

On development systems, the file is recreated on every request, see [bigace:developer:environment](developer/environment).

Note: As all files will be merged into one, you could get into problems with referenced media (like background-images) when you combine files from different directories.

Note: When you deploy changes to your production system, don't forget to change the $uniqueID, otherwise the file will not be recreated. You could delete the cache file from the filesystem to recreate the file, but then your visitors browsers might still use a cached file and not see the changes.

-> Since BIGACE 3.0

## Attributes


*  **$basepath** - (__required__, string)
    The $basepath from where the files will be taken.

*  **$filenames** - (__required__, array)
    $filenames is an array of filenames, that will be merged together. The order is preserved.

*  **$uniqueID** - (optional, string)
    When the $uniqueID changes, a new file is created. Any time you apply changes to the files, make sure to change this value, so your users will see the change.

*  **$type** - (optional, string)
    The $type defines the kind of filetype you want to compress. Currently supported are 'css' and 'javascript'. Default: 'css'

## Example

This example shows to compress multiple CSS files into one.

	:::php
	<?php
	
	// generate cached and compressed css files to speed things up
	$cssCache = $this->fileMerge(
	    BIGACE_DIR_PUBLIC_CID.'default/',
	    array(
	        'style.css', 'extension.css', 'news.css'
	    ),
	    Bigace_Core::VERSION
	);
	
	?>
	
	`<link rel="stylesheet" href="<?php echo BIGACE_URL_PUBLIC_CID.'default/' . $cssCache; ?>`" type="text/css" media="screen, projection" />


### See also

*  [ViewHelper fileMerge() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_FileMerge.html)

*  [bigace:developer:environment](developer/environment)

*  [Web Performance Best Practices](http://code.google.com/intl/de/speed/page-speed/docs/rules_intro.html) - Tips from Google

*  [Best Practices for Speeding Up Your Web Site](http://developer.yahoo.com/performance/rules.html) - Tips from Yahoo

