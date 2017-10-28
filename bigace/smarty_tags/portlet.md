# {portlet}

The {portlet} TAG loads one portlet by its classname.

-> Since BIGACE 2.7.

## Attributes


*  **name** - (__required__, String)
    The classname of the portlet. (e.g. load the class system/classes/portlets/ToolPortlet.php  with "ToolPortlet")

*  **assign** - (__required__, String)
    The name of the template variable the value will be assigned to. 

*  **list** - (optional, array)
    The list of portlets where this portlet will be added to (see examples). If you set this parameter, the new portlet will be appended to the "list" and the "list" itself will be assigned to the template variable "assign" instead of the single portlet!

*  **params** - (optional, String)
    A comma separated list of key=value pairs to set as portlet parameter (e.g. params="uid=test,foo=bar").

## Example

**Note:** All exmaples will work with the SkypeOnlinePortlet which requires the parameter "uid". This "uid" reflects a valid skype username, so this portlet will probably not work as expected if you set an incorrect username! 

This example shows to load the SkypeOnlinePortlet and display it on a single page.

	:::html
	`<html>`
	`<head>`
	   `<title>`SkypeOnlinePortlet Test 1`</title>`
	`</head>`
	`<body>`
	   {portlet name="SkypeOnlinePortlet" assign="skypePortlet" params="uid=YourSkypeName"}
	   `<h2>`{$skypePortlet->getTitle()}`</h2>`
	   {$skypePortlet->getHtml()}
	`</body>`
	`</html>`


This example shows to load all configured portlets for the current page and then adds the SkypeOnlinePortlet. This might be interesting if you want a special portlet always to be loaded.

	:::html
	`<html>`
	`<head>`
	   `<title>`SkypeOnlinePortlet Test 2`</title>`
	   {portlets assign="myPortlets"}
	   {portlet name="SkypeOnlinePortlet" list=$myPortlets assign="myPortlets" params="uid=YourSkypeName"}
	   {foreach from=$myPortlets item="aPortlet"}
	     {$aPortlet->getJavascript()}
	   {/foreach}
	`</head>`
	`<body>`
	{foreach from=$myPortlets item="aPortlet"}
	   `<h2>`{$aPortlet->getTitle()}`</h2>`
	   {$aPortlet->getHtml()}
	{/foreach}
	`</body>`
	`</html>`



