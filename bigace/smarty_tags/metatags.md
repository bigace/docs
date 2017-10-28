# {metatags}

The {metatags} TAG renders HTML tags used in the HTML header.

The following meta tags will be generated:

*  title

*  meta name="description"

*  meta name="author"

*  meta name="robots"

*  meta name="generator"

*  link rel="canonical"

-> Since BIGACE 2.5.

## Attributes


*  **item** - (__required__, Item object)
    The Item to be used for generating meta tags.

*  **assign** - (optional, string)
    The name of the template variable the value will be assigned to.

*  **author** - (optional, string)
    The name of the author to be used.

*  **prefix** - (optional, string)
    The prefix to be prepended to every created TAG.

## Highlights

This TAG sends the following "action filter" as described [here](bigace/plugins):

*  [metatags](bigace/hooks/metatags)

*  [metatags_more](bigace/hooks/metatags_more)

The [SEO Plugin](bigace/extensions/seo) makes use of these filter. If you installed 
and activated it, your metatags output may vary from the provided example.

## Example

This example shows to use [{metatags}](bigace/smarty_tags/metatags) in your templates. 

	:::html
	`<html>`
	`<head>`
	{metatags item=$MENU prefix="   " author="Alice and Bob"}
	`</head>`
	`<body>`
	   Hello World
	`</body>`
	`</html>`


This will be rendered to something like this:

	:::html
	`<html>`
	`<head>`
	   `<title>`your menu title here`</title>`
	   `<meta name="description" content="your menu description here" />`
	   `<meta name="robots" content="index,follow" />`
	   `<meta name="generator" content="BIGACE 2.7" />`
	   `<meta name="author" content="Alice and Bob" />`
	`</head>`
	`<body>`
	   Hello World
	`</body>`
	`</html>`


