# {link_auth}

The {link_auth} TAG creates the URL to perform a login. Can be used for self-made login forms.

-> Since BIGACE 2.5.


## Attributes


*  **id** - (optional, int)
    The ID of the item to redirect to, after login. Default is current menu.

*  **language** - (optional, string)
    The language of the item to redirect to, after login. Default is current language.

## Example

This example shows a link to the login formular.

	:::html
	`<html>`
	`<head>`
	   `<title>`LOGIN - Example`</title>`
	`</head>`
	`<body>`
	   `<form action="{link_auth}" method="POST">`
	      Username: `<input type="text" name="UID">`
	      `<br/>`
	      Password: `<input type="password" name="PW">`
	      `<br/>`
		  <input type="submit" value="Login">
	   `</form>`
	`</body>`
	`</html>`

