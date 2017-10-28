# {portlets}

The {portlets} TAG enables your template to use the BIGACE Portlet system.

Make sure your design is marked with "Portlet support", otherwise your user won't see the Portlet Administration link.

## Attributes


*  **assign** - (__required__, string)
    The name of the template variable portlets will be assigned to.

*  **id** - (optional, int)
    The ID to load the portlets for. If not set the requested menu id will be used.

*  **lang** - (optional, int)
    The language to load the portlets for. If not set the requested menu language will be used.

*  **name** - (optional, string)
    The name of the portlet column to fetch (comma separated list if more than one is used). Skip this attribute if you just use one column!


## Examples

### Example 1 - one portlet column

This example shows how to display the portlets (one portlet column) for a template.

	:::html
	`<html>`
	`<head>`
	   `<title>`Portlets for {$MENU->getName()}`</title>`
	   {portlets assign="myPortlets"}
	   {foreach from=$myPortlets item="portlet"}
	       {$portlet->getJavascript()}
	   {/foreach}
	`</head>`
	`<body>`
	   `<div id="content">`
	      ... your content here ...
	   `</div>`
	
	   `<div id="portletColumn">`
	     {foreach from=$myPortlets item="portlet"}
	        {$portlet->getJavascript()}
	        `<h2>``<em>`{$portlet->getTitle()}`</em>``</h2>`
	        {$portlet->getHtml()}
	     {/foreach}
	   `</div>`
	`</body>`
	`</html>`


### Example 2 - two portlet columns

This example shows how to display two portlet columns in a template. The two columns for the design are configured in administration and have the names "sidebar" and "footer". 

Here we use the array function of the {portlet} tag.

	:::html
	`<html>`
	`<head>`
	   `<title>`Portlets for {$MENU->getName()}`</title>`
	   {portlets assign="myPortlets" name="sidebar,footer"}
	   {foreach from=$myPortlets.sidebar item="portlet"}
	       {$portlet->getJavascript()}
	   {/foreach}
	   {foreach from=$myPortlets.footer item="portlet"}
	       {$portlet->getJavascript()}
	   {/foreach}
	`</head>`
	`<body>`
	
	   `<div id="sidebar">`
	     {foreach from=$myPortlets.sidebar item="portlet"}
	        {$portlet->getJavascript()}
	        `<h2>``<em>`{$portlet->getTitle()}`</em>``</h2>`
	        {$portlet->getHtml()}
	     {/foreach}
	   `</div>`
	
	   `<div id="content">`
	      ... your content here ...
	   `</div>`
	
	   `<div id="footer">`
	     {foreach from=$myPortlets.footer item="portlet"}
	        {$portlet->getJavascript()}
	        `<h2>``<em>`{$portlet->getTitle()}`</em>``</h2>`
	        {$portlet->getHtml()}
	     {/foreach}
	   `</div>`
	`</body>`
	`</html>`


## Links



*  See this [german forum thread](http://forum.bigace.de/templates/mehrere-portlet-bereiche/)
