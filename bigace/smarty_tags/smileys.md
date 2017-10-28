# {smileys}

The {""|smileys} modifier parses a string to replace all textual smileys with icons.

This modifier is part of the [Smileys Plugin](extensions/modul/smileys).

## Attributes


*  **textual** - (optional, boolean)
    Whether the string is parsed for extended smileys like **:band:** and **:lol:** or only for the well known smileys like **;)**. Default is false, only standard smileys will be replaced.

## Example

This example shows how to replace the Smileys in a string.

	:::html
	`<html>`
	`<head>`
	   `<title>`A simple Smiley string`</title>`
	`</head>`
	`<body>`
	   {"Some Smileys: :) :lol: :hbd: :-D"|smileys:true}
	`</body>`
	`</html>`


This example shows how to parse the 5 latest comments [{comments_latest}](smarty_tags/comments_latest):

	:::html
	`<html>`
	`<head>`
	   `<title>`Simple smileys in comments`</title>`
	`</head>`
	`<body>`
	   {comments_latest end="5" assign="myComments"}
	   {foreach from=$myComments item="comment"}
		<div class="comment"> <a name="comment{$comment.id}"></a>
			<div class="commentMeta"><span class="commentName">{$comment.name}</span> 
			{if $comment.homepage != ''}(<a{if $comment.anonymous} rel="nofollow"{/if} href="{$comment.homepage}" target="_blank">Web</a>){/if} 
			Written at {$comment.timestamp|date_format:"%m.%d.%y, %H:%M"}:
			</div>
			<p>{$comment.comment|nl2br|smileys}<hr /></p>
		</div>
	   {/foreach}
	`</body>`
	`</html>`



