# {bigace_copyright}

The {bigace_copyright} TAG echos a `<div>`...`</div>` with the proper BIGACE Copyright information, name of the Author, BIGACE Version and URL to the Homepage.

## Attributes

This TAG has no attributes.

## Example

	:::html
	`<html>`
	`<head>`
	   `<title>`Example`</title>`
	`</head>`
	`<body>`
	  Some content...
	  {bigace_copyright}
	`</body>`
	`</html>`


## CSS

Customize the Look by adding CSS for the following generated HTML:

	:::html
	`<div class="CopyrightFooter" align="center">``<span class="copyright">`...`</span>``</div>`


For example: 

	:::css
	.CopyrightFooter {
	   border-top:1px solid #cccccc;
	   background-color:#eeeeee;
	   padding-top:4px;
	   padding-bottom:4px;
	}
	 
	span.copyright, span.copyright a{
	   color: #666666;
	   font-size: 12px;
	}

