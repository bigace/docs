# Social Bookmarks

This plugin displays social bookmarking icons (and links) for the most important english services.

It was developed using template [bigace:developer:hooks](bigace/developer/hooks) and content [filter](bigace/developer/hooks).

Please read below for information how to include the Social-Bookmark menu in your pages.


`<WRAP center round download>`

Get all downloads from:

[Social-Bookmarks detail page](http://www.bigace.de/plugins/detail/44-Social+Bookmarks)

`</WRAP>`

## Installation


*  Upload the ZIP using the Extensions Administration

*  Activate the Plugin

*  Check if you need to customize your template to use this plugin (see Usage)

*  When your template is ready and the plugin activated, you should be able to see the social-bookmark links

## Screenshot

Please note, that the message in the screenshot comes from the template. You can add whatever message you want to display just before the SocialBookmarks are rendered.

{{:bigace:extensions:addon:social-bookmarks.jpeg|Social Bookmarks Screenshot}}

## Usage (version 0.4 and above)

This version uses the new parse_content filter
To use this Plugin your template needs to use the [bigace:smarty_tags:metatags](bigace/smarty_tags/metatags) TAG, which will receive all required Javascript and CSS declarations.

The Plugin replaces the string "[socialbookmarks]" with the menu, so you should either put that string into your template (as seen below) or you can add it to single pages by putting that string into the pages content.

	:::html
	`<html>`
	`<head>`
	  {metatags item=$MENU}
	`</head>`
	`<body>`
	  ... your content ...
	  `<h3>`Share the love:`</h3>`
	  [socialbookmarks]
	`</body>`
	`</html>`


## Usage (up to version 0.3)

If you do not use the default template Blix, you need these actions in your template:

*  {hooks_action name='[smarty_tpl_header](bigace/developer/action/smarty_tpl_header)' item=$MENU}

*  {hooks_action name='[smarty_tpl_footer](bigace/developer/action/smarty_tpl_footer)' item=$MENU}

	:::html
	`<html>`
	`<head>`
	  {hooks_action name="smarty_tpl_header" item=$MENU}
	`</head>`
	`<body>`
	  ... your content ...
	  `<h3>`Share the love:`</h3>`  
	  {hooks_action name="smarty_tpl_footer" item=$MENU}
	`</body>`
	`</html>`


