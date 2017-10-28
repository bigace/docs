# {sitename}

The {sitename} displays the configured Sitename.

-> Since BIGACE 2.5.

## Attributes


*  **default** (optional, string)
    This string will ONLY be returned if the configuration could not be found.

## Configuration

To change the sitename, open your [Configurations](manual/configurations) and change the key **community** / **sitename**.

## Example

This example shows the sitename as part of the browser title.

	:::html
	`<html>`
	`<head>`
	   `<title>`{$MENU->getName()} | {sitename}`</title>`
	`</head>`
	`<body>`
	   Hello World.
	`</body>`
	`</html>`

