# {link_item_languages}

The {link_item_languages} creates (and optional displays) links to all item language versions.

-> Since BIGACE 2.5

## Attributes


*  **item** -  (__required__, Item)
    The item to display links for

*  **assign** - (optional, string)
    The name of the template variable the links will be assigned to, if not set the links are echo'ed

*  **spacer** - (optional, string)
    The spacer between the languages

*  **delimiter** - (optional, string)
    The delimiter between the passed locales

*  **css** - (optional, string)
    Classname to be applied to links

*  **hideActive** - (optional, string)
    Do not show active language link (default false)

*  **images** - (optional, boolean)
    If set to false the language names will be displayed (default: true)

*  **locale** - (optional, string)
    The locale to display the language names in

*  **directory** - (optional, string)
    Folder where the images are taken from (optional)

*  **names** - (optional, boolean) - *added with 2.7*
    Whether to show the language name in the link (default: true). If you set "names" and "images" to false, "names" will be resetted to true! 

## Example

This example shows how to .

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   `<p>`All languages of the current page `<b>`{$MENU->getName()}`</b>`:`</p>`
	   {link_item_languages item=$MENU}
	`</body>`
	`</html>`

