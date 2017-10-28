# {modul}

The {modul} TAG loads (and executes) a module by name or if no name given, the current menus module.

-> Since BIGACE 2.2.

## Attributes


*  **menu** - (optional, Item)
    The menu to load the configured modul for. In most templates that will be $MENU.

*  **name** - (optional, string)
    The name of the module to load. If not set, we lookup the current menu and load its configured module.

*  **language** - (optional, string)
    The language to load modules translations with. If not set, uses the language from the current request.


## Example

This example shows how to load the menus module.

	:::html
	`<html>`
	`<head>`
	   `<title>`Module of {$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   {modul}
	     OR 
	   {modul name=$MENU->getModulID()}
	`</body>`
	`</html>`


This example shows how to load a special module.

	:::html
	`<html>`
	`<head>`
	   `<title>`Loading the module :contactMail:`</title>`
	`</head>`
	`<body>`
	   {modul name="contactMail"}
	`</body>`
	`</html>`

