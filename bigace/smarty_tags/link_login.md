# {link_login}

The {link_login} TAG creates the URL to the Login Formular.

-> Since BIGACE 2.3.


## Attributes


*  **id** - (optional, int)
    The ID of the item to redirect to, after login. Default is current menu.

*  **language** - (optional, string)
    The language of the item to redirect to, after login. Default is current language.

*  **redirectID** - (optional, string) *- since 2.4*
    Deprecated, use the "id" attribute instead.

*  **redirectCMD** - (optional, string) *- since 2.4*
    The command to redirect to, after login. Default is "smarty" for normal menu browsing.

*  **redirectURL** - (optional, string) *- since 2.4*
    A full URL to redirect to, after login. If set, the "redirectID" and "redirectCMD" attributes will be ignored.

## Example

This example shows a link to the login formular.

	:::html
	`<html>`
	`<head>`
	   `<title>`LOGIN - Example`</title>`
	`</head>`
	`<body>`
	   `<a href="{link_login}">`Login`</a>`
	`</body>`
	`</html>`


For a full "admin links" example, see [bigace:smarty_tags:permission_editcontent](smarty_tags/permission_editcontent).
