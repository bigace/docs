# {breadcrumb}

The {breadcrumb} TAG shows a Breadcrumb navigation. The bredcrumb is the way back from the current site, up to the Top Level Page (Home).

-> Since BIGACE 2.1.

FIXME complete all attributes



## Attributes

If "assign" is set, the HTML rendered breadcrumb will not be returned!


*  **assign** - (optional, int)
    Assigns the array with the items on the breadcrumb to the given template variable.

*  **id** - (optional, int)
    The ID from where the breadcrumb starts. Default is the current item id.

*  **language** - (optional, String)

*  **top** - (optional, int)

*  **css** - (optional, String)

*  **prefix** - (optional, String)

*  **suffix** - (optional, String)

*  **counter** - (optional, String)
    Assigns the amount of items on the breadcrumb to a template variable.

*  **hidden** - (optional, boolean)

## Example

This example shows a ...

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   {breadcrumb id=$MENU->getID() suffix='»'}
	`</body>`
	`</html>`

