# {tip_of_the_day}

The {tip_of_the_day} TAG fetches or assign a random "tip".
See 
The available "tips" will be configured in the Administration

-> Since BIGACE 2.4 and extension version 1.3.

## Attributes


*  **assign** - (__required__, string)
    The name of the template variable the tip will be assigned to.

## Example

This example shows how to fetch and display a tip.

	:::html
	{tip_of_the_day assign="tip"}
	`<html>`
	`<head>`
	   `<title>`Tip of the Day - Example usage`</title>`
	`</head>`
	`<body>`
	   Name: {$tip->getName()} `<br>`
	   {if $tip->getLink() != ''}
	   Link: `<a href="{$tip->`getLink()}">{$tip->getLink()}`</a>` `<br>`
	   {/if}
	   Text: {$tip->getTip()}
	`</body>`
	`</html>`

