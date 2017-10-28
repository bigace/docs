# {stylesheet}

The {stylesheet} TAG returns the URL of the goven Smarty Stylesheet.

-> Since BIGACE 2.4.

## Attributes


*  **name** - (__required__, string)
    The name of the Stylesheet to load, as shown in the Stylesheet Administration.

*  assign - (optional, string)
    The name of the template variable the URL will be assigned to. If not set, the URL will be returned by the TAG (default).

## Example

This example shows how to use the {stylesheet} TAG to load a custom CSS.

	:::html
	`<html>`
	`<head>`
	   `<title>`Stylesheet Example`</title>`
	   `<link href="{stylesheet name="blix_stylesheet_main"}" rel="stylesheet" type="text/css" />`
	`</head>`
	`<body>`
	   {tag_name}
	`</body>`
	`</html>`

