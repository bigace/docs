# {content}

The {content} TAG display additional content blocks of a page.

-> This TAG changed its usage with 2.5. If you used it before, please have a look [here](http://www.bigace.de/upgrade-2.5.html) and at the [{modul}](bigace/smarty_tags/modul) TAG.

Please note that you **cannot** read the pages default content with this TAG, it reads the additional configured content blocks.

## Attributes


*  **name** - (required, int)
    The name of the content you entered in the design assistent nd that is visible in the content editor.

*  **item** - (optional, Item)
    The item to load the content for OR you supply "id" and "language" (item is the preferred way!).

*  **id** - (optional, int)
    The Item ID to load the content for. Needs "language" to be set. Ignored if "item" is set.

*  **language** - (optional, string)
    If language locale to load content for. Needs "id" to be set. Ignored if "item" is set.

*  **language** - (optional, string)
    If language locale to load content for. Needs "id" to be set. Ignored if "item" is set.

## Example

This example shows how to load a content block.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   {content item=$MENU name="example"}
	`</body>`
	`</html>`


## Screenshot

This shows, how your design needs to be configured, to work with editor and {content} TAG.

{{bigace:smarty_tags:page-design.jpg}}
