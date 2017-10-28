# languageChooser()

FIXME document all attributes for Bigace 3.0

The **languageChooser** ViewHelper does something ...

-> Since BIGACE 3.0

Further infos at the [ViewHelper languageChooser() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_LanguageChooser.html).

## Attributes


*  **$languages** - (__required__, array)
    The $languages array define the list of languages to be displayed. If languages is null or an empty array, all available languages will be loaded.

*  **$options** - (optional, array)
    The $options define an key-value array of options for the resulting HTML.
    
Options can be one or many of these:

*  title (boolean, default: false) whether to include the language name in the link

*  alt (string)

*  spacer (string)

*  css (string)

*  locale (string)

*  directory (string)

*  active (string)

*  hideActive (boolean, default: false) whether to hide the current active language

*  images (boolean, default: true) whether to use images as link items

## Example

This example shows a simple lanagage chosser, that renders all languages with default settings.

	:::php
	<?php
	
	  echo $this->languageChooser();
	
	?>


