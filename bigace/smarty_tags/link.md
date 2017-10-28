# {link}

The {link} TAG creates an URL to link to any Item.

-> Since BIGACE 2.1.



## Attributes


*  **item** - (__required__, Item)
    Required attribute only if the id/language or url parameter are missing, otherwise it is optional. The Item itself could for exmaple be fetched with the [{load_item}](smarty_tags/load_item) TAG.

 OR


*  **id** - (optional, int)
    The ID of the Item to link.

*  **command** - (optional, String)
    The command to be used for linking (for menus use "smarty", for images "image"...).

 OR


*  **url** - (optional, String) - *since 2.4*
    The Unique URL of the Item to link to.


 The language Parameter will apply to each of the above mentioned parameter:


*  **language** - (optional, String)
    The item language to link to. This is the short locale (for example: english = "en", german = "de").




## Example

This example shows some simple Item links.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	{load_item itemtype="1" id="-1" assign="topLevel"}
	   `<ul>`
	      `<li>``<a href="{link id="-1" command="smarty"}">`TOP LEVEL`</a>``</li>`
	      `<li>``<a href="{link id="-1" command="smarty" language="en"}">`TOP LEVEL (english)`</a>``</li>`
	      `<li>``<a href="{link item=$topLevel}">`TOP LEVEL`</a>``</li>`
	      `<li>``<a href="{link url="sitemap.html"}">`Sitemap`</a>``</li>`
	   `</ul>`
	`</body>`
	`</html>`


Create a single link to the page with the ID 7.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	{load_item itemtype="1" id="7" assign="myPage"}
	`<a href="{link item=$myPage}">`{$myPage->getName()}`</a>`
	`</body>`
	`</html>`


