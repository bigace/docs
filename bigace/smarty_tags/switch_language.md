# {switch_language}

The {switch_language} TAG displays links to switch the Users session language.
This will be most often used for switching the navigation, but has the side effect, that all translations will be loaded in the new language.

If you want to switch the navigation language ONLY, you should instead use the "language" attribute of the [{link language="en"}](link) TAG for example.

-> Since BIGACE 2.3.



## Attributes


*  **languages** - (__required__, String)
    Comma separated list of locales. The delimiter can be changed using the "delimiter" attribute.

*  **hideactive** - (optional, boolean)
    Whether the current Session language is hidden or not. Default is "false".

*  **locale** - (optional, String)
    The locale to fetch the language names for. Default is the session language.

*  **images** - (optional, boolean) *- since 2.4*
    If set to "false" the language names will be displayed instead of the Image icons. Default is "true".

*  **directory** - (optional, String)
    Where the images are taken from. Default is "/public/system/images/".

*  **spacer** - (optional, String) *- since 2.4*
    The String inserted between two language links. Default is a space " ". 

*  **delimiter** - (optional, String) *- since 2.4*
    The delimiter to split the "languages" String. Default is a comma ",".

## Example

This example shows language links (Icons) to switch between German and English, hiding the current used one.

	:::html
	`<html>`
	`<head>`
	   `<title>`Switch language TAG`</title>`
	`</head>`
	`<body>`
	   {switch_language languages="de,en" hideActive="true"}
	`</body>`
	`</html>`


This example shows language links (Names) to switch between German and English, hiding the current used one. The language name is always display in english.

	:::html
	`<html>`
	`<head>`
	   `<title>`Switch language TAG`</title>`
	`</head>`
	`<body>`
	   {switch_language languages="de,en" images="false" hideActive="true" locale="en"}
	`</body>`
	`</html>`

