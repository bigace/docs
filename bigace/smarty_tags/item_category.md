# {item_category}

The {item_category} TAG returns an array with all the linked Cartegories of an given Item.

-> Since BIGACE 2.4.

## Attributes


*  **assign** - (__required__, string)
    The name of the template variable the value will be assigned to.

*  **id** - (__required__, int)
    The Menu ID to load the Categories for.

*  **id** - (optional, Item)
    If ID is not set, the Item MUST be set, to load the Categories for.

*  **itemtype** - (optional, int)
    If Itemtype to load Categories for. Default is Menu. => Parameter exists since 2.5.

## Example

This example shows how to load the Categories for the current Menu and display some information.

	:::html
	`<html>`
	`<head>`
	   `<title>`Fetching Categories`</title>`
	`</head>`
	`<body>`
	   {item_category item=$MENU assign="itemCategories"}
	   Categories for `<b>`{$MENU->getName()}`</b>`:
	   `<br>`
	   `<ul>`
	   {foreach item="cat" from=$itemCategories}
	      `<li>`[ID {$cat->getID()}] - {$cat->getName()} - {$cat->getDescription()}`</li>`
	   {/foreach}
	   `</ul>`
	`</body>`
	`</html>`


Check if a Menu has the Category with ID 2 assigned:

	:::html
	{item_category item=$MENU assign="itemCategories"}   
	  {foreach item="cat" from=$itemCategories}
	     {if $cat->getID() == 2} 
	        {assign var="category" value="$cat"}
	     {/if}
	  {/foreach}
	
	  {if isset($category)}
	     Menu has Category "{$category->getName()}" and ID "{$category->getID()}"!
	  {else}
	     Menu is not linked to category 2 :(
	  {/if}

