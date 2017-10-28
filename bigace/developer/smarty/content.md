# Smarty TAGs in Page content

If you want to display dynamic information within the pages content, you have to use a small "hack", which is not officially added to BIGACE.

Its a simple security reason why this function is not added to the Core system. But I'll come back to this later. 

First, lets have a look at the required code. If you know Smarty and the BIGACE API, its quite simple to achieve.
Search your template and find the part where the pages module is loaded, which is normally done by using the [{modul}](bigace/smarty_tags/modul) TAG. For example:

	:::html
	`<div id="content">`
	  {modul}
	`</div>`


Now, the required code, that replaces the above one:

	:::html
	`<div id="content">`
	{if $MENU->getModulID() == "displayContent"}
	  {assign var="myURL" value=$MENU->getFullURL()}
	  {include file="file:$myURL"}
	{else}
	  {modul menu=$MENU}
	{/if}
	`</div>`


Simple as that :D

But lets come back to the security issue. If you know Smarty, you know that there are a couple of functions, that might be a risk, if you can't trust the content editors. There is the TAG {php} (refer to the offical docu: http://www.smarty.net/manual/de/language.function.php.php) which allows to execute any PHP code.
Or simply the {include} Statement, which could be used to display some configuration files...

If you are the only person editing the code, fine, you can normally trust yourself ;)
But think about the risks as well, when you activate this feature!
