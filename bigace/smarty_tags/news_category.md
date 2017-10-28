# {news_category}

The {news_category} TAG returns or displays all Categories the given News was published with.

If you are looking for a way to display all available News categories, see [{news_categories}](smarty_tags/news_categories).

-> Since BIGACE 2.4 and [News](extensions/addon/news) v0.9.


## Attributes


*  **item** - (required, News Item)
    The News Item, we lookup the Categories for. This OR the "id" attribute must be set.

*  **id** - (required, int)
    The News ID, we lookup the Categories for. This OR the "item" attribute must be set.

### Fetch Category array

Use "assign", if you want to fetch an array of Category items:


*  **assign** - (optional, string)
    The name of the template variable the array with Categories will be assigned to.

### Display list of Category links

If you do not want to handle the categories in your template, use the easy method and pass:


*  **css** - (optional, string)
    The CSS class to apply for every category link.

*  **prefix** - (optional, string)
    The HTML prefix to display BEFORE each category.

*  **suffix** - (optional, string)
    The HTML suffix to display AFTER each category.

*  **last** - (optional, string)
    If set, the "last" attribute replaces the "suffix" attribute for the last category.

## Example

This example shows how the default list (comma separated items) is rendered:

	:::html
	`<html>`
	`<head>`
	   `<title>`How to display the NewsItem categories...`</title>`
	`</head>`
	`<body>`
	    {news_item id=$MENU->getID() assign="newsPage"}
	    The News with the title: `<b>`{$newsPage->getTitle()}`</b>` has been filed under the categories:
	    `<br>`
	    {news_category item=$newsPage}
	`</body>`
	`</html>`


Display the list a bit more complex:

	:::html
	`<html>`
	`<head>`
	   `<title>`How to display the NewsItem categories...`</title>`
	   `<style type="text/css">`
	   a.newsPage {
	      font-size:14px;
	      text-decoration:underline;
	      color:red;
	   }
	   `</style>`
	`</head>`
	`<body>`
	    {news_item id=$MENU->getID() assign="newsPage"}
	    The News with the title: `<b>`{$newsPage->getTitle()}`</b>` has been filed under the categories:
	    `<br>`
	    `<ul>`
	    {news_category item=$newsPage prefix="`<li>`" suffix="`</li>`" css="categoryLink"}
	    `</ul>`
	`</body>`
	`</html>`


The last example is for the experienced user and uses the returned category array, instead of pre-rendered HTML:

	:::html
	`<html>`
	`<head>`
	   `<title>`How to fetch the NewsItem categories...`</title>`
	`</head>`
	`<body>`
	    {news_item id=$MENU->getID() assign="newsPage"}
	    The News with the title: `<b>`{$newsPage->getTitle()}`</b>` has been filed under the categories:
	    `<br>`
	    `<ul>`
	    {news_category item=$newsPage assign="newCategories"}
	    `<ul>`
	      {foreach from=$newCategories item="curCat"}
	         `<li>``<b>`{$curCat->getName()}`</b>` - {$curCat->getDescription()}`</li>`
	      {/foreach}
	    `</ul>`
	`</body>`
	`</html>`

