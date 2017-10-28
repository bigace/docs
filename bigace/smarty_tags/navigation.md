# {navigation}

The {navigation} TAG returns the pre-rendered HTML of a navigation.


## Attributes


*  **id** - (optional, int)
    The ID to load the children Items from. Default is the current Menus ID.

*  **language** - (optional, string)
    The Itemtype to load the Item from. Default is the current Menus language.

*  **css** - (optional, string)
    The CSS class to use for a link (`<a class="">`).

*  **selected** - (optional, string)
    The CSS class to use for the active Item. If not set the "css" attribute is used.

*  **active** - (optional, string)
    If set, this replaces the "prefix" parameter for the active item.

*  **prefix** - (optional, string)
    The prefix for each link (rendered before the opening link `<a>` TAG)

*  **suffix** - (optional, string)
    The suffix for each link (rendered after the closing link `</a>` TAG)

*  **last** - (optional, string)
    If set, this replaces the "suffix" parameter for the very last item in the list.

*  **start** - (optional, string)
    The HTML prefix to start the rendering with.

*  **end** - (optional, string)
    The HTML to append at the very end of the rendering process.

*  **counter** - (optional, string)
    The amount of items the navigations had. This value will be assigned to the named Smarty variable.

*  **activeInTree** - (optional, boolean)
    If set to "true" this searches the items subtree for the active Item. Caution: This can be a performance problem on huge sites or in big navigation trees.


## Examples

The most common use case, a **main navigation including a link to your homepage** (change the language if required!):

	
	  {load_item itemtype="1" id="-1" assign="topLevel" language="en"}
	  `<ul id="navigation">`
	  `<li>``<a href="{link item=$topLevel">`{$topLevel->getName()}`</a>``</li>`
	  {navigation id=$topLevel->getID() language=$topLevel->getLanguageID() prefix="`<li>`" suffix="`</li>`"}
	  `</ul>`


### Top Level

This example loads the Top menu and shows its name and the childs as unordered list.

	:::html
	`<html>`
	`<head>`
	   {load_item itemtype="1" id="-1" assign="topLevel"}
	   `<title>`Navigation Example for {$topLevel->getName()}`</title>`
	`</head>`
	`<body>`
	   The Menu `<b>`{$topLevel->getName()}`</b>` has the following Sub Items:`<br>`
	   {navigation id=$topLevel->getID() language=$topLevel->getLanguageID() start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`" counter="amount"}
	   `<br>`
	   It has {$amount} child(s).
	`</body>`
	`</html>`


### Current menu

This example loads the current menu menu and shows its name and the childs as unordered list.

	:::html
	`<html>`
	`<head>`
	   `<title>`Navigation Example for {$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   The Menu `<b>`{$MENU->getName()}`</b>` has the following Sub Items:`<br>`
	   {navigation id=$MENU->getID() language=$MENU->getLanguageID() start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`" counter="amount"}
	   `<br>`
	   It has {$amount} child(s).
	`</body>`
	`</html>`



### A dedicated menu

This example loads the menu with the ID 10 in english and shows its name and the childs as unordered list.
Please note: This example might not work at your system, if the page does not exist. Then change then ID and language to a page on your system that has children.

	:::html
	`<html>`
	`<head>`
	   `<title>`Navigation Example`</title>`
	`</head>`
	`<body>`
	   The Menu with ID `<b>`10`</b>` in `<b>`english`</b>` has the following children:`<br>`
	   {navigation id="10" language="en" start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`" counter="amount"}
	   `<br>`
	   It has {$amount} child(s).
	`</body>`
	`</html>`


### A complex navigation example

This example works with two and three level systems. It displays a top level navigation including a HOME link.
If the current page is one of the toplevel menus, the css class "current" is appended like `<a href="menuLink" class="current">`.

If you navigate to one of the subpages, their children are displayed in the `<div id="subMenu">`.

At the pages end, a simple footer menu is displayed, where you need to replace "Your-Footer-ID-here" with an existing Menu ID.


	:::html
	`<html>`
	`<head>`
	   `<title>`Complex Navigation Example`</title>`
	`</head>`
	`<body>`
	 `<div id="topmenu">`
	   `<ul>`
	   {load_item itemtype="1" id="-1" assign="topLevel"}
	   `<li>``<a href="{link item=$topLevel}"{if $MENU->`getID() == $topLevel->getID()} class="current"{/if}>{$topLevel->getName()}`</a>``</li>`
	   {navigation id=$topLevel->getID() language=$topLevel->getLanguageID() prefix="`<li>`" suffix="`</li>`" selected="current"}
	   `</ul>`
	  `</div>`
	
	  `<div id="content">`
	     ... put your content here...
	  `</div>`
	
	  `<div id="subMenu">`
	    {if $MENU->getParentID() == -1}
	      {navigation id=$MENU->getID() language=$MENU->getLanguageID() start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`"}
	    {elseif $MENU->getParentID() > -1}
	      {navigation id=$MENU->getParentID() language=$MENU->getLanguageID() start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`"}
	    {/if}
	    ... more menu column stuff here ...
	  `</div>`
	
	  `<div id="footer">`
	   {load_item itemtype="1" id="Your-Footer-ID-here" assign="footer"}
	   {navigation id=$footer->getID() language=$footer->getLanguageID() start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`"}
	  `</div>`
	`</body>`
	`</html>`


