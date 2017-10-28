# Smarty for Bigace

Smarty is one of the most popular template eingines in the PHP world. In Bigace 2.x it was the default template engine, as in Bigace 3 it is available as extension.

Here are some articles related to Smarty, which were originally written for Bigace 2.x:


*  [Smarty Templates](./smarty/tutorial) - create a design, Step-by-Step

*  [Smarty Tags](smarty_tags) - for templates customization & dynamic data

*  [TAGs in page content](./smarty/content) - for these special situations...

*  [Smarty external](./smarty/external) - using templates in your applications

*  ["Previous page" & "Next page"](./smarty/previousnextpage) - create these links using Smarty TAGs

## Using web resources

To load resuorces like images and CSS files in your template, you need the [{directory}](smarty_tags/directory) TAG:

	:::html
	`<link rel="stylesheet" type="text/css" href="{directory}styles.css" />`
	`<script type="text/javascript" src="{directory}script.js">``</script>`


The [{directory}](smarty_tags/directory) returns the path to your communities web directory.

If you created your template using a extension, you might be using a subfolder. Make sure to append it in this case:

	:::html
	`<link rel="stylesheet" type="text/css" href="{directory}mytheme/styles.css" />`
	`<script type="text/javascript" src="{directory}mytheme/script.js">``</script>`


This will expand to:

	:::html
	`<link rel="stylesheet" type="text/css" href="http://yourdomain/public/cid1/mytheme/styles.css" />`
	`<script type="text/javascript" src="http://yourdomain/public/cid1/mytheme/script.js">``</script>`


## Inline styles and scripts

Smarty uses the {} brackets as identifier for [template tags](smarty_tags). You will notice that using inline CSS or Javascript like ...

	:::css
	`<style type="text/css">`

	* {margin:0px; padding:0px;}
	body { background-color: #eeeeee; }
	`</style>`
	`<script type="text/javascript">`
	function sayHello(name) {
	   alert("Hello "+name);
	}
	sayHello("World");
	`</script>`


... will result in something like ...

	:::html
	`<style type="text/css">`

	* body `</style>`
	`<script type="text/javascript">`
	function sayHello(name) sayHello("World");
	`</script>`


... which is definitely not what you wanted. Smarty tries to interpret everything between an open { and a closing } bracket as tag, strips it out and dumps an error in the bigace log if couldn't handle it.

Now the solution is to tell the template engine that it shouldn't parse parts of the template by using the {literal} tag:

	:::css
	{literal}
	`<style type="text/css">`

	* {margin:0px; padding:0px;}
	body { background-color: #eeeeee; }
	`</style>`
	`<script type="text/javascript">`
	function sayHello(name) {
	   alert("Hello "+name);
	}
	sayHello("World");
	{/literal}
	`</script>`


Now Smarty nows, that it should leave everything between {literal} and {/literal} untouched.

Please read the about delimiter and the literal tag in the official documentation.

## Template Skeleton

When you start to create a new template, you might want to consider to use this HTML skeleton, which includes best practices.

	:::html
	`<html>`
	`<head>`
	    `<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />`
	    {metatags item=$MENU}
	`</head>`
	`<body>`
	  `<div class="header">`
	    `<h1>`{sitename}`</h1>`
	  `</div>`
	  
	  `<div class="content">`
	    `<h2>`{$MENU->getName()}`</h2>`
	    {modul menu=$MENU}
	  `</div>`
	      
	  `<div class="footer">`
	    &copy; Copyright {$smarty.now|date_format:"%Y"} {configuration package="community" key="copyright.holder" default="BIGACE CMS"}. All rights reserved.
	    `<br />`
	    Powered by {bigace_version link=true full=true}. 
	    {if $USER->isAnonymous()}
	        | `<a rel="nofollow" target="_self" href="{link_login id=$MENU->`getID()}">Login`</a>`
	    {else}
	        `<br/>`
	        `<a target="_blank" href="{link_admin id=$MENU->`getID()}">Administration`</a>` | 
	        {permission_editcontent assign="allowEditor"}
	        {if $allowEditor}
	         `<a href="{link_editor id=$MENU->`getID() language=$MENU->getLanguageID()}" target="_blank">Editor`</a>` | 
	        {/if}
	        `<a target="_self" href="{link_logout id=$MENU->`getID()}">Logout`</a>`
	    {/if}
	  `</div>`
	`</body>`
	`</html>`   


## See also

[Smarty documentation](http://www.smarty.net/manual/index.php) 


