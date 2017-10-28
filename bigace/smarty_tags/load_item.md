# {load_item}

The {load_item} TAG loads an Item and assigns this to a given Smarty variable name.

## Attributes


*  **itemtype** - (required, string)
    The Itemtype to load the Item from

*  **id** - (required, int)
    The ID of the Item to be loaded

*  **language** - (optional, string)
    The language locale to load. Default: current sites language

*  **assign** - (required, string)
    The name of the Smarty variable that should be assigned

## Example

This example loads the Top menu and shows its content.
Further infos about the available Item functions can be found in the [PHP API](bigace/php_api).

	:::html
	`<html>`
	`<head>`
	   {load_item itemtype="1" id="-1" assign="topLevel"}
	   `<title>`{$topLevel->getName()}`</title>`
	`</head>`
	`<body>`
	   {$topLevel->getContent()}
	`</body>`
	`</html>`

