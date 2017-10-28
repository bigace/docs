# {thumbnail}

The {thumbnail} TAG creates a URL to a dynamically created Image thumbnail.

-> Since BIGACE 2.4 RC2.

## Attributes


*  **id** - (__required__, int)
    The ID of the Image to create the thumbnail for.

*  language - (optional, string)
    The languages of the Image to load.

*  height - (optional, int)
    The height of the thumbnail.

*  width - (optional, int)
    The width of the thumbnail.

*  assign - (optional, string)
    The name of the template variable the value will be assigned to.

If "height" and "width" is not set, the normal Image will be displayed.
If only of of them is set, the other one is calculated automatically (what is the preferred way, set only one of "width" OR "height").



## Example

This example displays a thumbnail for the Image with the ID 5 and the new width of 100 pixel. The height will be automatically calculated.

	:::html
	`<html>`
	`<head>`
	   `<title>`Image thumbnail`</title>`
	`</head>`
	`<body>`
	   `<img src="{thumbnail id=5 width=100}" alt="Thumbnail">`
	`</body>`
	`</html>`

