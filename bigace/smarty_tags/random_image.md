# {random_image}

The {random_image} TAG fetches random filesnames from a directory.

This feature can be useful for example when creating an image slider.

## Attributes


*  **assign** - (__required__, int)
    The name of the template variable the array of filenames will be assigned to.

*  **dir** - (__required__, string)
    The directory to load files from..

*  **extensions** - (optional, string)
    A comma separated list of file extensions which that should be used when searching files. Defaults to "gif,png,jpg,jpeg".

*  **amount** - (optional, int)
    Amount of maximum files that should be returned. Defaults to 1. If less files were found, all found will be returned.

## Example

This example shows a simple example, where we fetch 5 images from the folder /public/cid1/slider/:

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   `<ul>`
	       {directory name="stylesheets" assign="imgDir"}
	       {random_image amount="5" dir="$imgDir/slider/" assign="images"}          
	       {foreach from=$images item="imgFile"}
	          `<li>``<img src="{directory}slider/{$imgFile}" height="110" alt="" />``</li>`
	       {/foreach}
	   `</ul>`
	`</body>`
	`</html>`

