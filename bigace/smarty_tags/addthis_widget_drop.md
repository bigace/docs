# {addthis_widget_drop}

The {addthis_widget_drop} TAG shows the ADD This widget at the page where you put it to.

The AddThis Widget shows bookmarking links to the most important social bookmarking sites.

See a demo at: http://www.addthis.com/

-> Since BIGACE 2.5 (probably)

Please note: If you want to use statistics you need to put in your AddThis username, which has nothing todo with your BIGAEC username! You must register at http://www.addthis.com/register first. To watch your statistics you need to login at the AddThis website as well!

## Attributes


*  username - (optional, string)
    A username for statistic purpose

*  link - (optional, string)
    The URL to be bookmarked (if passed, 'item' will be ignored)

*  item - (optional, Item)
    The item which should be bookmarked (will be ignored if 'link' is set)

*  title - (optional, string)
    Name for the bookmark (if not set, the URL will be used)

## Example

This example shows how to add a default AddThis widget with activated statistics.

	:::html
	`<html>`
	`<head>`
	   `<title>`AddThis for {$MENU->getName()}`</title>`
	`</head>`
	`<body>`
	   {addthis_widget_drop username="dummy" item=$MENU}
	`</body>`
	`</html>`

