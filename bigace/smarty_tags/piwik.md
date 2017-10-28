# {piwik}

The {piwik} TAG allows easy user statistics through [Piwik - the Open source web analytics](http://piwik.org) software.

-> Since [SEO 0.7](bigace/extensions/seo).

## Attributes


*  **id** - (__required__, int)
    The ID of your Piwik website.

*  **assign** - (optional, int)
    The name of the template variable the value will be assigned to.

*  **path** - (optional, string)
    The full URL of your Piwik installation (only the path, see example 2).

*  **track_user** - (optional, boolean)
    Whether logged in user will be tracked (default: false).

*  **track_links** - (optional, boolean)
    Whether clicked links will be tracked (default: true).

## Installation

If you do not have a running Piwik installation yet, follow this short installation list:
 1.  download piwik 
 2.  extract the ZIP file
 3.  create a folder /addon/piwik/
 4.  upload all files to /addon/piwik/
 5.  install piwik
 6.  create your first website in Piwik (which will likely get the ID 1)

If you already have Piwik running, skip this step and see Example 2.

## Example

This example shows the usage of Piwik installed in /addon/piwik/ with your Website configured as ID 1 (in Piwik).

	:::html
	`<html>`
	`<head>`
	   `<title>`Piwik tracking`</title>`
	`</head>`
	`<body>`
	   {piwik id="1"}
	`</body>`
	`</html>`


This example shows the usage of Piwik installed in a differetn place (or even domnain) with your Website configured as ID 5 (in Piwik).

	:::html
	`<html>`
	`<head>`
	   `<title>`Piwik external tracking`</title>`
	`</head>`
	`<body>`
	   {piwik path="http://www.example.com/piwik/" id="5"}
	`</body>`
	`</html>`

