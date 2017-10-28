# {bigace_version}

The {bigace_version} TAG returns an Version String. Depending on the parameters, it returns the proper Software name and link to the BIGACE Homepage.

## Attributes

This TAG has only optional attributes:


*  **full** (optional, boolean)
    The version string will start with the correct Software name.

*  **build** (optional, boolean)
    The version string will include the internal used Build ID.

*  **link** (optional, boolean)
    The version string will be returned as HTML link (`<a href=...>`version string`</a>`)

## Example

	:::html
	`<html>`
	`<head>`
	   `<title>`Example`</title>`
	`</head>`
	`<body>`
	  This site is running: {bigace_version full="true"}.`<br/>`
	  Click the following lnk to visit the Homepage of: {bigace_version full="true" link="true"}.`<br/>`
	  The internal version of your BIGACE installation is: {bigace_version full="true" build="true"}.`<br/>`
	`</body>`
	`</html>`

