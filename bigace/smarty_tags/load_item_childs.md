# {load_item_childs}

The {load_item_childs} TAG fetches the children items of a specified menu.

-> Since BIGACE 2.2.

## Attributes


*  **assign** - (__required__, int)
    The name of the template variable the array will be assigned to.

*  **id** - (optional, int)
    The ID to load the children Items from. Default is the current Menu ID.

*  **language** - (optional, string)
    The language to load the Item. Default is the current menu language.

*  **counter** - (optional, string)
    The amount of items that will be returned. This value will be assigned to the named Smarty variable.

## Example

This example shows a preview of the current menus children with `<h1>`Menu Name`</h1>` and the description as teaser, followed by a link to open the full article. If no description is saved the default value "No teaser available..." will be shown instead.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	 {load_item_childs id=$MENU->getID() assign="preview"}
	 {foreach from=$preview item="currentPage"}
	 `<h1>`{$currentPage->getName()}`</h1>`
	 `<p>`{$currentPage->getDescription()|default:"No teaser available..."} `<a href="{link item=$currentPage}">`~~Read more~~`</a>``</p>`
	 {/foreach}
	`</body>`
	`</html>`


## Example 2

The next - more complex - example shows how to show a 2-3 level menu tree, starting with all menus below the HOME page.
If the current page is a 2nd or 3rd level menu, we display the 3rd level as well.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	 {load_item_childs id="-1" assign="level1"}
	 `<ul>`
	 {foreach from=$level1 item="currentPage"}
	 `<li>``<a href="{link item=$currentPage}">`{$currentPage->getName()}`</a>`
	   {load_item_childs id=$currentPage->getID() assign="level2"}
	   {if count($level2) > 0}
	     `<ul>`
	     {foreach from=$level2 item="currentPage2"}
	     `<li>``<a href="{link item=$currentPage2}">`{$currentPage2->getName()}`</a>`
	       {if $MENU->getID() == $currentPage2->getID() || $MENU->getParentID() == $currentPage2->getID()}
	       {load_item_childs id=$currentPage2->getID() assign="level3"}
	       {if count($level3) > 0}
	         `<ul>`
	         {foreach from=$level3 item="currentPage3"}
	         `<li>``<a href="{link item=$currentPage3}">`{$currentPage3->getName()}`</a>``</li>`
	         {/foreach}
	         `</ul>`
	       {/if}
	       {/if}
	     `</li>`
	     {/foreach}
	     `</ul>`
	   {/if}
	 `</li>`
	 {/foreach}
	 `</ul>`
	`</body>`
	`</html>`


## Example 3

Display a simple one-level navigation with CSS classes, to replace the text with images. 

NOTE: This examples uses the page field "catchwords". You have to fill in the CSS class name for each page!

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	 {load_item_childs id=-1 assign="topNavi"}
	 `<ul class="topNavi">`
	  {foreach from=$topNavi item="currentPage"}
	    `<li class="{$currentPage->`getCatchwords()}">`<a href="{link item=$currentPage}">`{$currentPage->getName()}`</a>``</li>`
	   {/foreach}
	  `</ul>`
	`</body>`
	`</html>`


Now let say we have three pages below TopLevel:
 1.  Profile  (cacthwords: about)
 2.  Contact  (catchwords: contact)
 3.  Impress  (catchwords: impress) 

Then you have to add some CSS, like this:

	:::css
	ul.topNavi {list-style-type: none;}
	ul.topNavi a { text-indent: -9999px; }
	ul.topNavi .about { background: url(profile.jpg) 0 0 no-repeat; }
	ul.topNavi .contact { background: url(contact.jpg) 0 0 no-repeat; }
	ul.topNavi .impress { background: url(impress.jpg) 0 0 no-repeat; }


As you can see, we move the text inside each link away. Doing this, we only see the image, but search engines still see the name of the page (which is pretty important for your ranking in search results!).
