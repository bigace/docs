# parse_content

The parse_content [filter](developer/hooks) will be executed after a Smarty (or PHP) Template was rendered. It receives the complete HTML output and the menu as parameter and can replace parts of the content dynamically.

This filter is ONLY called for rendered pages.

Since Bigace 2.7.5 (see [Jira Ticket](http://dev.bigace.org/jira/browse/BIGACE-47))

## Declaration

The filter is called like this:

	:::php
	echo Hooks::apply_filters('parse_content', $html, $MENU);


Here $html is the rendered page and $MENU is the menu that is displayed.

## Example plugin

This example filter replaces the string "[google]" with the Google Logo:

	:::php
	Hooks::add_filter('parse_content', 'myContentFilter', 10, 2);
	
	function myContentFilter($html, $MENU)
	{
	    return str_replace('[google]', `<img src="http://www.google.com/images/logos/ps_logo2.png" alt="Google Logo" />`, $html);
	}


## See also


*  [bigace:developer:hooks](developer/hooks)

*  Writing [bigace:developer:plugins](developer/plugins) to extend Bigace


