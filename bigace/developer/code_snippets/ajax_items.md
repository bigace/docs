# AJAX Item Information

BIGACE comes with some Applications that use AJAX, for example the JS Menu Chooser or the Menu Administration (Menu Tree).

There is (for now only a small) AJAX API that can be used when developing your own applications.

## Getting Item Information

To fetch Item Information, you simply have to add some lines of Code to your Script:

	:::html
	  `<script type="text/javascript" src="<?php echo $GLOBALS['_BIGACE']['DIR']['public']; ?>`system/javascript/ajax_xml.js">`</script>`
	  `<script type="text/javascript" src="<?php echo $GLOBALS['_BIGACE']['DIR']['public']; ?>`system/javascript/bigace_ajax.js">`</script>`
	  `<script type="text/javascript">`
	  function getItem(itemid, languageid)
	  {
	      var itemRequestUrl = "`<?php echo ApplicationLinks::getAjaxItemInfoURL(_BIGACE_ITEM_MENU, '"+itemid+"', '"+languageid+"'); ?>`";
	      return loadItem(itemRequestUrl, false);
	  }
	  `</script>`


The returned Javascript Object has not the same methods as the PHP API. Some methods are missing, some methods are new. 

Please have a look at "/public/system/javascript/bigace_ajax.js" for more information.
