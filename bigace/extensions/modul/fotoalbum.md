# Photo-Album

The HTML Photo-Album is a "old fashioned" [Fotogallery](extensions/modul/fotogallery) using pure HTML.

The gallery displays all images of one category in a list.
On the left side is the thumbnail of the image, on the right side is the name and description of the image. 
There is also a detail link, so you get a new full-detail page for each image. On the detail page you get the image in full-size includng description and name.

Its easy to style the gallery to a unique look by adding your own CSS rules to your stylesheet. Please cheack the sourcecode of the rendered gallery to find out which CSS classes can be used. Or check the example below...

`<WRAP center round download>`

Get all downloads from:

[Photo-Album detail page](http://www.bigace.de/plugins/detail/57-Photo+Album)

`</WRAP>`

## Installation


*  Install the extension

*  Create a category "test"

*  Upload at least one image and assign the category "test" to it

*  Assign the module "Photo Album" to a page

*  Open the page - you will see a message "that the module is not yet configured"

*  Click the "Configure Album" link - a PopUp opens

*  Choose the category "test" in the PopUp dialog and save 

*  Close the dialog 

*  Reload the page - the images should be visible now

## Screenshots

{{:bigace:extensions:modul:photoalbum-preview.jpeg|Preview of the gallery in a default layout}}

{{:bigace:extensions:modul:photoalbum-preview-styled.jpg|Gallery with custom CSS}}

{{:bigace:extensions:modul:photoalbum-module-settings.jpeg|The module settings dialog}}

## CSS example

	:::css
	.fotoEntry {
	    color: #666666;
	    font-size: 13px;
	    line-height: 1.6;
	    margin-bottom: 10px;
	}
	.fotoEntry img {
	    margin-right: 20px;
	    -moz-border-radius: 5px 5px 5px 5px;
	    -moz-box-shadow: 0 0 20px #787878;
	    background: none repeat scroll 0 0 #F9F9F9;
	    border: 1px solid #AAAAAA;
	    padding: 5px;
	}
	.fotoEntry a {
	    color: #5C91C7;
	}

