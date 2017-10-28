# {load_translation}

The {load_translation} TAG loads a file with translations into the translation namespace.

## Attributes


*  **name** - (__required__, string)
    The name of the languae file to load.

*  **locale** - (optional, string)
    The language (locale) of the file to load. Default is the environment language.

*  **directory** - (optional, string)
    The directory to lookup the translation files. Default locations will be searched afterwards automatically.

## Example

This example shows how to load the "editor" translation which is located at **/system/languages/en/editor.properties**.

	:::html
	`<html>`
	`<head>`
	   `<title>`Load a translation file and display a translated string.`</title>`
	`</head>`
	`<body>`
	   {load_translation name="editor"}
	   {Translation of the key "content_page" is: `<b>`{translate key="content_page"}`</b>`.
	`</body>`
	`</html>`

