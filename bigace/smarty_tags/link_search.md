# {link_search}

The {link_search} TAG crates the URL to the Search result page and will be likely used in a quick search formular.

See the "[Customizing Search](administration/search)" article as well for more information about request parameter.

## Attributes


*  **id** - (optional, int)
    The menu id that will be used for rendering the search.

*  **language** - (optional, string)
    The language locale to display the search result page.

## Example

This example shows a minimal quick search form:

	:::html
	`<html>`
	`<head>`
	   `<title>`Search BIGACE pages`</title>`
	`</head>`
	`<body>`
	   `<form action="{link_search id=$MENU->`getID()}" method="post">
	       `<input type="text" name="search" value="" />`
	       `<input type="hidden" name="language" value="{$MENU->`getLanguageID()}" />
	       `<input type="submit" value="Search" id="searchbutton" name="searchbutton" />`
	    `</form>`
	`</body>`
	`</html>`

