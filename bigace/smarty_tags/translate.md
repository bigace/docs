# {translate}

The {translate} TAG returns a String, representing the translation of the requested key. This translation can be piped through sprintf, for text replacements.

## Attributes


*  **key** - (required, string)
    The key to be fetched from the translation file.

*  **default** - (optional, string)
    The string to be returned if the key could NOT be found.

*  **namespace** - (optional, string)
    The namespace to fetch the translation from.

*  **sprintf** - (optional, string)
    One or more arguments for the replacement. If the number of arguments is lower than in the translated string, nothing will be returned.

    * **delimiter** - (optional if sprint is set, string)
    The delimiter string, that separates the sprintf arguments. Default is (,) comma.

## Example

	:::html
	{load_translation name="example"}
	`<html>`
	`<head>`
	   `<title>`{translate key="title"}`</title>`
	`</head>`
	`<body>`
	  {translate key="welcome" sprintf=$USER->getName()}!
	
	  {translate key="intro" sprintf="username,$USER->getName()"}
	  {translate key="intro2" sprintf="email:root@localhost" delimiter=":"}
	`</body>`
	`</html>`

