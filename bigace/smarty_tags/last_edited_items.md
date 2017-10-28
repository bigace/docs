# {last_edited_items}

The {last_edited_items} TAG renderes or returns the last edited pages/images/files.

-> Since BIGACE 2.3.


## Attributes



*  **itemtype** - (optional, int) - Possible values: 1 for pages, 4 for images, 5 for files. Default: 1.

*  **id** - (optional, int) - Fetch only items below a special ID (only use with menus if you want to show items of a special subtree)

*  **language** - (optional, string) - Language of the items that will be fetched.

*  **from** - (optional, int) - If you want to use paging, the start value.

*  **to** - (optional, int) - If you want to use paging, the end value.

*  **order** - (optional, string) - How the items should be orderer (ASC/DESC).

*  **assign** - (optional, string) - Name of the template variable the value will be assigned to.

*  **pre** - (optional, string)

*  **post** - (optional, string)

*  **preDate** - (optional, string)

*  **postDate** - (optional, string)

*  **description** - (optional, string)

*  **date** - (optional, string)



## Example

This example shows how to fetch the last edited pages as pre-rendered HTML.

	:::html
	`<html>`
	`<head>`
	   `<title>`Last edited pages`</title>`
	`</head>`
	`<body>`
	   {last_edited_items}
	`</body>`
	`</html>`


This example shows how to fetch the last edited images as pre-rendered HTML.

	:::html
	`<html>`
	`<head>`
	   `<title>`Last edited images`</title>`
	`</head>`
	`<body>`
	   {last_edited_items itemtype="4"}
	`</body>`
	`</html>`



This example shows how to fetch the last edited images as pre-rendered HTML.

	:::html
	`<html>`
	`<head>`
	   `<title>`Last edited images gallery`</title>`
	`</head>`
	`<body>`
	  {last_edited_items itemtype="4" from="0" to="3" assign="myLastImage"}
	  {foreach from=$myLastImage item="img"}
	  `<div class="image">`
	    `<a href="{link item=$img}">``<img src="{link item=$img}" alt="{$img->`getName()}">
	    `<br />`
	    `<b>`{$img->getName()}`</b>` - {$img->getDescription()}`</a>`
	  `</div>`
	  {/foreach}
	`</body>`
	`</html>`


