# How to write new Designs

This article covers the first steps in creating a new Template & Design for your website.
Follow the instructions in the given order and you will have a usable (no, not pretty: usable!) design afterwards.

Start with logging in and switching to Administration -> Layout.

# Stylesheet

Open "Stylesheet" and create a new Stylesheet by passing:


*  the name "ExampleCSS"

*  an optional description "Stylesheet for education"

*  the Editor Stylesheet "dummy_stylesheet" for the beginning

Hit the create icon and post the following code into the editor:

	:::css
	body { background-color: #7bb000; font-family: Verdana, Geneva, Arial; }
	h1 { font-size:16px; font-weight:bold; border-bottom:2px dotted orange; width:650px; padding-left:10px; }
	#content { font-size:12px; width:640px; padding-left:20px; color: #000000; border-bottom:2px dotted orange; }
	#navigation li { display:inline; }
	#navigation a { font-size:12px; color:#ffffff; font-weight:bold; }
	#content {}
	#logo {}
	#header {}
	#footer  {}


Now save it and change the Administration to "Templates".

# Smarty Template

Create a new Template by passing:


*  the name "Example-Template"

*  an optional description "Template for educational work"

*  check the Template radio button (switch from include to template)

Hit the create icon to open the new templates detail page.

Add following content into the template editor:

	:::html
	`<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">`
	`<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="{$MENU->`getLanguageID()}" lang="{$MENU->getLanguageID()}">
	{load_item id="-1" itemtype="1" assign="topLevel"}
	`<head>`
	    `<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />`
	   `<link rel="stylesheet" href="{stylesheet name="ExampleCSS"}" type="text/css" media="screen, projection" >`
	   {metatags item=$MENU}
	`</head>`
	`<body>`
	   `<div id="header">` 
	       `<span id="logo">``<a href="{link item=$topLevel}">`{sitename|htmlspecialchars}`</a>``</span>`
	       `<ul id="navigation">`
	           {navigation prefix="`<li>`" suffix="`</li>`" counter="amount"}
	       `</ul>`
	   `</div>`
	
	   `<div id="content">`
	       `<h1>`{$MENU->getName()}`</h1>`
	       {modul menu=$MENU}
	   `</div>`
	   
	   `<div id="footer">`
	   {if $USER->isAnonymous()}
	      `<a href="{link_login id=$MENU->`getID()}">{translate key="login"}`</a>`
	   {else}
	      {permission_editcontent assign='allowEditor'}
	      {if $allowEditor}
	         `<a target="_blank" href="{link_editor id=$MENU->`getID() language=$MENU->getLanguageID()}">Edit page`</a>` |
	      {/if}
	      `<a target="_blank" href="{link_admin}">`Administration`</a>` | 
	      `<a href="{link_logout id=$MENU->`getID()}">Logout`</a>`
	   {/if}
	   `</div>`
	`</body>`
	`</html>`


Before saving the Template check the radio button **Template ready (choosable for new Designs)**.

For a "real world" template you might need a lot more [Smarty TAGs](bigace/smarty_tags). 


Last point is to create a design, which then can be assigned to menus. 
Change to Administration: "Page Design".

# Design

Create a new Design by passing:


*  the name "Example-Design"

*  an optional description "Design for educational work"

*  the previous created stylesheet "ExampleCSS"

*  and the template "Example-Template"

After creation, using the create icon, change to the menu administration.

# Assign the new Design

Open the Menu Administration and edit the **Top Level** Page. Assign the Layout **Example-Design** and save the page.
Now hit the **Preview Button** and the menu will be displayed ... in green, orange and black and white LOL.

Thats all, should be done in 20 minutes even without experience.
Have fun and post your experience about this article in the Forum or improve it, if you find any mistake!

Please read the page [bigace:developer:smarty](bigace/developer/smarty) carefully and check out the default template skeleton.
