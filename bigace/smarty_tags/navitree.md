# {navitree}

The {navitree} TAG renders a navigation (and its childs).

## Attributes


*  **id** - (__required__, int)
Needed to render its childs as navigation.


*  **language** - (optional, int)
default: site-language


*  **css** - (optional, string)
CSS for each navigation element.
*default: NULL*


*  **selected** - (optional, string)
Replaces the CSS for the active navigation element.
*default: NULL*


*  **activeintree** - (optional, bool)
Shows a CSS-Navtrail.
*default: FALSE*


*  **start** - (optional, string)
Tag (or something else) that starts before the whole navigation.
*default: NULL*


*  **end** - (optional, string)
Tag (or something else) that ends after the whole navigation.
*default: NULL*


*  **prefix** (optional, string)
Tag (or something else) that appears before each navigation element.
*default: NULL*


*  **suffix** (optional, string)
Tag (or something else) that appers after each navigation element.
*default: NULL*


*  **subprefix** (optional, string)
Tag (or something else) that appers before each 2nd+ level navigation element.
*default: NULL*


*  **subsuffix** (optional, string)
Tag (or something else) that appers after each 2nd+ level navigation element.
*default: NULL*

    
## Definitions

The {navitree}-TAG renders automaticly for 2nd level navigation elements 
`<li class='level1' style='padding-left: 6px;'>`{html}
before it displays defined stuff.

For each 3rd level navigation elements it renders:
`<li class="level2" style="padding-left:10px;">`{html}

You have to keep that in mind, while using it (adding .level2 and .level1 to your CSS File). Otherwise you can also change the smarty class.

## Code Example

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   {load_item itemtype="1" id="-1" assign="topLevel"}
	   {navitree id=$topLevel->getID() language=$topLevel->getLanguageID() 
	start="`<ul>`" end="`</ul>`" prefix="`<li>`" suffix="`</li>`" selected="current" 
	activeintree="TRUE"}
	`</body>`
	`</html>`

