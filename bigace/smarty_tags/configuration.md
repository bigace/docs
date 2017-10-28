# {configuration}

The {configuration} TAG enables you to read Configuration entrys, that are accessable in the Administration at System -> Configurations.

-> Since BIGACE 2.2.

## Attributes


*  **package** - (optional, String)
    The name of the package to read the config entry from.

*  **key** - (optional, String)
    The name of the configuration entry to read.

*  **assign** - (optional, String)
    This name of the template variable, the config value will be assigned to.

*  **default** - (optional, String)
    This value to return, if the requested configuration entry could not be found.

*  **cache** - (optional, String)
    This name of the configuration package to cache (use it, if you read more than 3 config entrys from the same package).

## Example 1

Caching a Config package for multiple access:

	:::html
	{configuration cache="system"}
	`<html>`
	`<head>`
	   `<title>`Using the {configuration} TAG`</title>`
	`</head>`
	`<body>`
	   `<p>`Display extended footer: {configuration package="system" key="footer.type.extended"}`</p>`
	   `<p>`Log Level: {configuration package="system" key="logger.loglevel"}`</p>`
	   `<p>`Using Smarty: {configuration package="system" key="use.smarty" default=true}`</p>`
	`</body>`
	`</html>`


## Example 2

Assigning a config entry for later usage:

	:::html
	`<html>`
	`<head>`
	   `<title>`Using the {configuration} TAG`</title>`
	`</head>`
	`<body>`
	   {configuration package="custom" key="tree.id" default="-1" assign="rootID"}
	
	   `<p>`The below tree will be loaded from ID: {$rootID}`</p>`
	
	   {load_item_childs id=$rootID assign="myTree"}
	
	  ... do further stuff with the tree ...
	
	`</body>`
	`</html>`

