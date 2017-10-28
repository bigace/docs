# Links to "Previous" and "Next" page

This article discribes how to implement the function to click forward and backward between the pages of a current menu.

**Note:** \\
This code does not use to split content to dispose it over an amount of different pages (e.g. the output of a database-query). For this purpose use **SmartyPaginate**.

Add the following Code to your template:

    {load_item_childs id=$MENU->getParentID() assign="sisters"}
    {if count($sisters) > 0}
    {foreach from=$sisters item="cur"}
      {if isset($last) && $last->getID() == $MENU->getID()}
        {assign var="next" value="$cur"}
      {/if}
      {if !isset($next) && $cur->getID() != $MENU->getID()}
        {assign var="prev" value=$cur}
      {/if}
      {assign var="last" value=$cur}
    {/foreach}
    {/if}

**Explanation:**\\
This code figures out, wether the current page has got sister-pages (in other words: whether there are more pages in the current menu), and if, which of them is the previous ("$prev") and which the next one ("$next").

Finally the "items"("$prev" and "$next") need to be linked:

    {if isset($prev) || isset($next)}
    `<div>`
      {if isset($prev)}
        `<a href="{link item=$prev}">`previous page`</a>`
      {/if}
      {if isset($next)}
        `<a href="{link item=$next}">`next page`</a>`
      {/if}
    `</div>`
    {/if}

Instead of the words "previous page" and "next page" you may want to use images (e.g. arrows):

    `<img src="path/to/prev.png">`
    `<img src="path/to/next.png">`

The rest will do bigace for you...
