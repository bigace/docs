# {link_locale}

The {link_locale} TAG creates the URL to switch the Session language.

-> Since BIGACE 2.5.


## Attributes


*  **locale** - (required, string)
    The locale to switch to. For example "en" or "de".

*  **id** - (optional, string)
    The Menu ID to redirect to after switching the language.

## Example

This example shows a link to switch the language between German and English.

	:::html
	`<html>`
	`<head>`
	   `<title>`Session language switch - Example`</title>`
	`</head>`
	`<body>`
	  {if $MENU->getLanguageID() == "en"}
	    `<a href="{link_locale locale="de"}">`Show in Germany`</a>`
	  {else}
	    `<a href="{link_locale locale="en"}">`Show in English`</a>`
	  {/if}
	`</body>`
	`</html>`

