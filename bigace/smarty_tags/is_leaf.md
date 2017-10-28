# {is_leaf}

The {is_leaf} TAG returns whether an item has children or not.
This tag returns only useful information for menu items.

-> Since BIGACE 2.5.

## Attributes


*  **item** - (__required__, Item)
    The item to fetch information for. See examples.

*  **assign** - (optional, string)
    The name of the template variable the boolean will be assigned to. If not set, the boolean will be returned.

## Example

This example demonstrates how to check if the current page has children.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   {is_leaf item=$MENU assign="hasChildren"}
	   {if $hasChildren}
	     The current menu has children!
	   {else}
	     The current menu has no children!
	   {/if}
	`</body>`
	`</html>`

