# {news_item}

The {news_item} TAG loads one single News item.

-> Since BIGACE 2.4 and installed [News](extensions/addon/news) [Extension](extensions).

## Attributes


*  **id** - (__required__, int)
    The ID of the News item to load.

*  **assign** - (__required__, string)
    The name of the template variable the News item will be assigned to.

## Example

This example shows how to load a News item and its linked image. The News item is represented by the current page (but you could replace $MENU->getID() easily with any News ID you want to).

	:::html
	`<html>`
	`<head>`
	   `<title>`I am a News`</title>`
	`</head>`
	`<body>`
	   {news_item id=$MENU->getID() assign="NEWS"}
	   {load_item itemtype=4 id=$NEWS->getImageID() assign="newsImage"}
	   `<h1>`{$NEWS->getTitle()}`</h1>`
	   `<p>``<a href="{link item=$newsPage}" title="{$newsImage->`getName()}">`<img src="{link item=$newsImage}" style="float:left">``</a>`
	      `<b>`{$NEWS->getTeaser()}`</b>``</p>`
	   `<p>`{$NEWS->getContent()}`</p>`
	`</body>`
	`</html>`

