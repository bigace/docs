# {link_admin}

The {link_admin} TAG returns thr absolute URL to the Administration.

-> Since BIGACE 2.1.


## Attributes


*  **id** - (optional, int)
    The ID of the admin menu/panel to load. 

*  **language** - (optional, int)
    The language in which the administration framework will be loaded.

## Description

To access the administration, you don't need to set one of these values. 
But if you pass an ID, which does not exist, you get an "File not found" screen!

If you want to access the administration framework skip the ID attribute! 
You don't want to hear? ;-) Then pass "index" or "-1" as ID.

## Example

This displays a link to the Administration, depending on the users login state.

	:::html
	`<html>`
	`<head>`
	   `<title>`Administration link`</title>`
	`</head>`
	`<body>`
	  {if $USER->isAnonymous()}
		<a target="_self" href="{link_login}">Login</a>
	  {else}
		<a target="_blank" href="{link_admin}">Administration</a> &middot; 
		<a target="_self" href="{link_logout}">Logout</a>
	  {/if}
	`</body>`
	`</html>`


For a full "admin links" example, see [bigace:smarty_tags:permission_editcontent](bigace/smarty_tags/permission_editcontent).
