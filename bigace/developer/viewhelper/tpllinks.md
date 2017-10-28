# tplLinks()

The **tplLinks** ViewHelper returns stateful URLs to actions that can be useful in your [bigace:developer:zendtemplate](bigace/developer/zendtemplate).

-> Since BIGACE 3.0

## Attributes


*  **$item** - (__required__, Bigace_Item)
    The $item to fetch the URLs for. 

*  **$user** - (__required__, Bigace_Principal)
    The $user to fetch the URLs for. Defaults to the current user.

The returned array can hold the following entries:

*  login - url for the login formular

*  logout - url to logout

*  editor - url to edit the $item in an editor

*  admin - url to open the administration dashboard

*  widget - url to open the widget administration

*  search - url to perform a search and/or show the search

Note: The array only contains links to actions the user is allowed to use (for example editor is only set when the $user is allowed to use an editor and has permissions for the $item).

## Example

This example shows to fetch and display action links in a [bigace:developer:zendtemplate](bigace/developer/zendtemplate).

	:::php
	<?php
	
	// load most important links that we will use within the template
	$allLinks = $this->tplLinks($this->MENU, $this->USER);
	
	if (isset($allLinks['login'])) {
	  echo `<a rel="nofollow" href="'.$allLinks['login'].'">`Login`</a>`;
	} else {
	  if (isset($allLinks['admin'])) {
	    echo `<a target="_blank" href="'.$allLinks['admin'].'">`Administration`</a>`;
	  }
	  if (isset($allLinks['editor'])) {
	    echo `<a target="_blank" href="'.$allLinks['editor'].'">`Edit page content`</a>`;
	  }
	  if (isset($allLinks['logout'])) {
	    echo `<a href="'.$allLinks['logout'].'">`Logout`</a>`;
	  }
	}
	
	?>


## See also

*  [ViewHelper tplLinks() PHPDoc](http://api.bigace-cms.com/latest/Bigace_Zend/View_Helper/Bigace_Zend_View_Helper_TplLinks.html)

*  [bigace:developer:zendtemplate](bigace/developer/zendtemplate)

