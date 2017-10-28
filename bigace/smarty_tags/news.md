# {news}

The {news} TAG loads a list of (categorized) News Items.

This TAG is normally used to display the latest News in a list, with a link to a News detail page.

-> Since BIGACE 2.4 RC1 and installed [News](extensions/addon/news) [Extension](extensions).


## Attributes


*  **assign** - (__required__, int)
    The name of the template variable the value will be assigned to.

*  category - (optional, string)
    A (comma separated) list of Category IDs, that will be used when fetching News. All News linked at least to one of these Categories will be returned.

*  counter - (optional, string)
    Name of the Template variable the amount of returned Items will be assigned to.

*  orderby - (optional, string)
    The column, the Items will be ordered by. Default is "createdate", what should normally apply in a News System...

*  order - (optional, string)
    The order of the returned Items. Possible values are "ASC" and "DESC".

*  start - (optional, int)
    Start Item, default is 0. Requires "end" or "limit" to be set.

*  end - (optional, int)
    Last Item, should be set when using "start" attribute.

*  limit - (optional, int)
    Replaces the "start" and "end" attribute. The amount of fetched News Items.

*  language - (optional, string)
    This parameter should NOT BE used, unless you REALLY know how the News System works!

*  hidden - (optional, boolean) -> *since News v1.1*
    If set to "true" this will show hidden (unreleased) news as well. Default is to hide them (false).

## Example

This example loads 3 News linked to the Category 1 and/or 2.

	:::html
	`<html>`
	`<head>`
	   `<title>`Fetching categorized News`</title>`
	`</head>`
	`<body>`
	   {news category="1,2" limit="3" assign="currentNews"}
	   {foreach from=$currentNews item="newsPage"}
	     `<h1>`{$newsPage->getTitle()}`</h1>`
	     `<b>`{$newsPage->getTeaser()}`</b>`
	     `<br>`
	     {$newsPage->getContent()}
	   {/foreach}
	`</body>`
	`</html>`


This example loads the latest 10 News and displays them in a list with the News image (as thumbnail) including title and teaser.
Click the image or the "more" link to display the full News.

	:::html
	`<html>`
	`<head>`
	   `<title>`Fetching 10 latest News`</title>`
	`</head>`
	`<body>`
	  `<div class="news">`
	    {news assign="currentNews" limit=10}
	    {foreach from=$currentNews item="newsPage"}
	      {load_item itemtype=4 id=$newsPage->getImageID() assign="newsImage"}
	      `<a href="{link item=$newsPage}" title="{$newsImage->`getName()}">
	        `<img src="{thumbnail id=$newsPage->`getImageID() width="100"}" class="newsThumbnail" alt="{$newsImage->getName()}" align="left">
	      `</a>`
	      `<h1>`{$newsPage->getTitle()}`</h1>`
	      `<p>`{$newsPage->getTeaser()} `<a href="{link item=$newsPage}">`more`</a>``</p>`
	    {/foreach}
	  `</div>`
	`</body>`
	`</html>`


