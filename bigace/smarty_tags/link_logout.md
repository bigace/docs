# {link_logout}

The {link_logout} TAG returns the URL to perform a logout for the current user.

After clicking the user will cmoe back to the current page, if he has read permissions.
Otherwise he will be redirected to the homepage.

-> Since BIGACE 2.5.

## Attributes


*  **item** - (optional, Item)
    The Item to redirect to.

*  **id** - (optional, int)
    The ID to redirect to.

*  **language** - (optional, String)
    The language to redirect to.

*  **cms** - (optional, String)
    The command to redirect to.

## Example

This example shows how to show a logout link.

	:::html
	`<html>`
	`<head>`
	   `<title>`LOGOUT - Example`</title>`
	`</head>`
	`<body>`
	   `<a href="{link_logout}">`Login`</a>`
	`</body>`
	`</html>`


For a full "admin links" example, see [bigace:smarty_tags:permission_editcontent](smarty_tags/permission_editcontent).
