# {google_analytics}

The {google_analytics} TAG dumps the required Javascript code for using the "new" Google Analytics Javascript snippet.

The TAG comes with the [SEO Extension](bigace/extensions/seo).

"New" vs. "Old" Google Analytics:


*  **ga.js** is the "new" way, which is __supported__ by this TAG

*  **urchin.js** is the "old" way, please upgrade using the Google Analytics tools

## Attributes


*  **id** - (__required__, string)
    The Google Analytics ID (UA-xxxxxx-x)

*  **assign** - (optional, string)
    The name of the template variable the value will be assigned to. If not set, the HTML will be dumped directly.

*  **track_user** - (optional, boolean)
    Flag whether logged in users should be tracked by Google Analytics. This is not recommended, so default is: **FALSE**

Please note that you will not see the GA javascript code if you are logged in into BIGACE without specifying **track_user=true**. Simply log off and reload your page.

## Example

This example shows how you normally use the {google_analytics} TAG.

	:::html
	`<html>`
	`<head>`
	   `<title>`Google Analytics`</title>`
	   {google_analytics id="UA-xxxxxx-x"}
	`</head>`
	`<body>`
	  Your content ...
	`</body>`
	`</html>`


This example shows how to log both anonymous AND registered users.

	:::html
	`<html>`
	`<head>`
	   `<title>`Google Analytics`</title>`
	   {google_analytics id="UA-xxxxxx-x" track_user=true}
	`</head>`
	`<body>`
	Registered and unregistered users will be logged. Registered users are users who are logged into the system!
	`</body>`
	`</html>`



