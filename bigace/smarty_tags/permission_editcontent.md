# {permission_editcontent}

The {permission_editcontent} TAG checks if the  something usefull.

-> Since BIGACE 2.5.

## Example

This example shows how to check permissions and display standard links:

If user is anonymous:

*  Login

If user is logged-in:

*  Editor (if user has permission)

*  Administration

*  Logout

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	
	`<div id="content">`
	  `<p>`Hellow World`</p>`
	  {modul menu=$MENU}
	`</div>`
	`<div id="footer">`
	  {if !$USER->isAnonymous()}
	    {permission_editcontent assign='allowEditor'}
	    {if $allowEditor}
	      `<a href="{link_editor id=$MENU->`getID() language=$MENU->getLanguageID()}">Editor`</a>` |
	    {/if}
	    `<a href="{link_admin}">`Administration`</a>` |
	    `<a href="{link_logout}">`Logout`</a>`
	  {else}
	    `<a href="{link_login}">`Login`</a>`
	  {/if}
	`</div>`
	`</body>`
	`</html>`

