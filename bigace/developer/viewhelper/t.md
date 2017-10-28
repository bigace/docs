# t()

The **t** ViewHelper is used for loading and fetching of translation strings.

-> Since BIGACE 3.0

## Attributes


*  **$key** - (optional, string)
    The $key defines the name of the translation.

*  **$default** - (optional, string)
    The $default string to return if $key could not be found. (Default: '' in which case '???'.$key.'???' will be returned)

__Function load():__


*  **$name** - (required, string)
    The $name defines the filename to load.

*  **$locale** - (optional, string)
    The $locale in which the translation file is loaded.
    
## Example

This example shows to fetch a translated String with the key 'search'.

	:::php
	<?php
	
	  echo $this->t('search');
	
	?>


This example shows to use a default string if the requested translation does not exist.

	:::php
	<?php
	
	  echo $this->t('not-existing', 'i will be echoed!');
	
	?>


This example shows how to load a translation file.

	:::php
	<?php
	
	  // loads the file 'bigace' in the current session language
	  $this->t()->load('bigace');
	
	  // loads the file in english
	  $this->t()->load('bigace', 'en');
	
	?>


## See also

*  [bigace:developer:translations](bigace/developer/translations)

*  [ViewHelper t() API](http://dev.bigace.org/api/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_T.html).

