# {comments_latest}

The {comments_latest} TAG fetches a number of latest comments, regardless of the topic they where posted for.


## Attributes


*  **assign** - (__required__, string)
    The name of the template variable, the comments array will be assigned to.

*  **order** - (optional, string)
    Possible values are "DESC" and "ASC". Default is "DESC".

*  **start** - (optional, int)
    The number of the first comment to fetch. Default is 0.

*  **end** - (optional, int)
    The number of the latest comment to fetch. Default is 10.

*  **itemtype** - (optional, int)
    The Itemtype fetch the comments for. Default is to ignore the Itemtype.

*  **itemid** - (optional, int)
    The Item ID to fetch the comments for. Default is to ignore the Item ID.

*  **language** - (optional, string)
    The language locale of the comments to fetch. Default is to ignore the language at all.




## Example

This example shows how to fetch the latest comments for all items on your website.

	:::html
	`<html>`
	`<head>`
	   `<title>`Latest comments`</title>`
	`</head>`
	`<body>`
	   {comments_latest assign="myComments"}
	   {foreach from=$myComments item="comment"}
		<div class="comment"> <a name="comment{$comment.id}"></a>
			{if $comment.activated == 0}
				<div class="commentHint">This posting is awaiting moderation.</div>  
			{/if}
			<div class="commentMeta"><span class="commentName">{$comment.name}</span> 
			{if $comment.homepage != ''}(<a{if $comment.anonymous} rel="nofollow"{/if} href="{$comment.homepage}" target="_blank">Web</a>){/if} 
			Written at {$comment.timestamp|date_format:"%m.%d.%y, %H:%M"}:
			</div>
			<p><img class="commentGravatar" src="{gravatar email=$comment.email width="40"}" width="40">{$comment.comment|nl2br}<hr /></p>
		</div>
	   {/foreach}
	`</body>`
	`</html>`

