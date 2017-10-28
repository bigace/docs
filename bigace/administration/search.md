# Search

If you want to customize the Look of your Search, you have change the two config values "templates/application.header" and "templates/application.footer". 

Since BIGACE 2.4 it is quite easy to integrate the Search into your Website design, cause it is completely based on Smarty now.



## Configuration

The following configuration keys are used by the Search:


*  **templates/application.header** the Template/Include to be used as header (usage depends on the Search template)

*  **templates/application.footer** the Template/Include to be used as footer (usage depends on the Search template)

*  **search/template** the Template/Include to be used for displaying the search and its results

In most cases, you should be able to displya the Search results in your page design, by using your header and footer includes!

## Search Templates

There are currently two templates used by the Search. The header displays everything BEFORE and the footer displays everything AFTER the search formular and results.

The following variables are independent from your real search:


*  $TPL_HEADER -> the application header template. not required to use, but recommended: {include file=$TPL_HEADER}

*  $TPL_FOOTER -> the application header template. not required to use, but recommended: {include file=$TPL_FOOTER}

*  $MENU -> the menu to use as current page (value depends on template, often the one the user came from)

*  $USER -> the current user

*  $TITLE -> the search title (could be used as browser title)

*  $CSS -> optional value (only for default template, you should use your own Stylesheet instead!)

*  $CHARSET -> the charset to display results (not required, but often used for metatags)

*  $ACTION_URL -> the URL to perform a new search (use in `<form action="">`)

The next values depend on whether a search was performed or not:


*  $itemtype -> the itemtype that was used for search

*  $searchTerm -> the search term 

*  $limit -> amount of maximum possible results (the amount of real results can easily be fetched by {count($results)})

*  $language -> the language in which results where searched (-1 for language independent search)

Last but not least:


*  $result -> the results of your query (see below for more information)

If you use a custom Template, you should use your own stylesheet by using the [{stylesheet}](bigace/smarty_tags/stylesheet) TAG.

You could even customize the complete Search formular and the Search result by editing the Template "APPLICATION-SEARCH".


## Search Formular

If you want to search from a global formular from your website, you can pass the following POST parameter:


*  search (optional: the search string)

*  language (optional: the language to search in)

*  itemtype (optional: where value might be 1,4 or 5)

*  limit (optional: the amount of maximum search results)

And here, for the ones more familiar with Copy & Paste LOL a simple search formular:

	:::javascript
	    `<script type="text/javascript">`
	    {literal}
	    function doQuickSearch()
	    {
	    	if(document.getElementById('s').value.length == 0) {
	            alert('Your searchterm is empty, please enter at least 4 character!');
	            return false;
	        }
	        else if(document.getElementById('s').value.length < 4) {
	            alert('Your searchterm is to short, please enter at least 4 character!');
	            return false;
	        }
		return true;
	    }
	    {/literal}
	    `</script>`
	    `<form action="{link_search id=$MENU->`getID()}" method="post" onSubmit="return doQuickSearch();">
	       `<fieldset>`
	       `<input type="text" name="search" value="" id="s" />`
	       `<input type="hidden" name="language" value="{$MENU->`getLanguageID()}" />
	       `<input type="submit" value="Search" id="searchbutton" name="searchbutton" />`
	       `</fieldset>`
	    `</form>`

Note: The Javascript could easily be skipped and is NOT required.

# Results

The returned results are an array of associative arrays:

	
	{foreach from=$results item="searchResult"}
	  `<p>`
	    `<a title="{$searchResult.name}" href="{$searchResult.url}">`{$searchResult.name}`</a>`:`<br>`
	    {$searchResult.description}
	    `</p>`
	{/foreach}


The following keys are (at least) set for each result:


*  id

*  name

*  description

*  language

*  unique_name

*  content (not the original content, only the content that was searched)

*  filename

*  url

*  mimetype

