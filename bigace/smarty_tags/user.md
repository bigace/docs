# {user}

The {user} TAG fetches a User object or returns a username, depending on the used attributes.

-> Since BIGACE 2.4.

## Attributes


*  **id** - (__required__, int)
    The User ID to lookup. One of "name" or "id" attribute is required.

*  **name** - (__required__, string)
    The Username to lookup. One of "name" or "id" attribute is required.

*  **assign** - (optional, string)
    The name of the template variable the user object will be assigned to.

## Example

This example shows how to display the author of a menu.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	`<h1>`{$MENU->getName()}`</h1>`
	`<div id="content">`
	{content}
	`</div>`
	`<p style="font-size: x-small;">`Written at {$MENU->getCreateDate()|date_format:"%B %d, %Y"} by {user id=$MENU->getCreateByID()}`</p>`
	`</body>`
	`</html>`



The next example shows how to display (some) information about a user.

	:::html
	`<html>`
	`<head>`
	   `<title>`User Details`</title>`
	`</head>`
	`<body>`
	{user name="admin" assign="principal"}
	`<h1>`Details for: {$principal->getName()}`</h1>`
	`<p>`ID: {$principal->getID()}`</p>`
	`<p>`Email: {$principal->getEmail()}`</p>`
	`<p>`Language: {$principal->getLanguageID()}`</p>`
	`<p>`Activated: {if $principal->isActive()}Yes{else}No{/if}`</p>`
	`</body>`
	`</html>`

