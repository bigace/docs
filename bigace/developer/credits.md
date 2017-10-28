# Credits

As developer you might be interested to add an entry to Bigace [bigace:manual:about](manual/about) screen. Doing that is possible through two ways:

 1.  copying an INI file to the folder ''/application/bigace/modules/admin/credits''
 2.  registering a listener for the [bigace:developer:filter:credits](developer/filter/credits) filter

If you write a PHP extension for Bigace, you should always choose to use the filter! If you don't have a Plugin, you can choose to use the INI way. But remember that INI files are rendered for every Community (even if they don't use your extension).

## Example: INI

Create the file ''/application/bigace/modules/admin/credits/foo.ini''

	:::ini
	title = "Foo - an INI exmaple for the Credits screen"
	
	[foo]
	weblink     = "http://www.bigace.de"
	copyright   = "Kevin Papst"
	description = "A longer description to explain your extension, that shipped this file. You can use HTML here, but don't use an apostrophe - only single quotes like this: `<a href='http://www.bigace.de'>`Bigace`</a>`."
	


## Example: Filter

Please read the filter docu of [bigace:developer:filter:credits](developer/filter/credits).

Remember that your [bigace:plugins](plugins) needs to be activated, otherwise the [Filter](developer/hooks) will not be executed.
