# {comment_counter}

The {comment_counter} TAG counts the amount of comments for an item.

If you do not pass the **assign** attribute, the amount will be returned directly, so you can put the TAG where you want the counter to be displayed.


## Attributes


*  **assign** - (optional, string)
    The template variable name where the value will be assigned to. If this is not set, the value will be returned.

*  **item** - (__required__, item)
    The item to count the comments for. If this is not passed, you must at least pass the **id** and **language** attribute.

*  **id** - (optional, int)
    The Item ID to count the comments for.

*  **language** - (optional, string)
    The Item language to count the comments for.

*  **itemtype** - (optional, int)
    The Itemtype to count the comments for. Default is "1" for menus.


## Example

This example shows how to fetch the comments for the current page.

	:::html
	`<html>`
	`<head>`
	   `<title>`Comment counter example`</title>`
	`</head>`
	`<body>`
	   The page "{$MENU->getName()}" has `<b>`{comment_counter item=$MENU}`</b>` comments.
	`</body>`
	`</html>`


This example shows how to assign the value to a variable to use it later.

	:::html
	`<html>`
	`<head>`
	   `<title>`Comment counter example`</title>`
	   {comment_counter item=$MENU assign="amount"}
	`</head>`
	`<body>`
	   The page "{$MENU->getName()}" has `<b>`{$amount}`</b>` comments.
	`</body>`
	`</html>`


This example shows how to fetch the comments for the english image with the ID 10.

	:::html
	`<html>`
	`<head>`
	   `<title>`Comment counter example`</title>`
	`</head>`
	`<body>`
	   The image has `<b>`{comment_counter itemtype="4" language="en" id="10"}`</b>` comments.
	`</body>`
	`</html>`

