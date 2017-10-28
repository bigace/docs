# {directory}

The {directory} TAG returns directorys, depending on your installation and configuration.

It recognizes whether you have de-/activated URL Rewriting and if you installed in a subdirectory or not.
The TAG creates absolute URLs, including the protocol **http://**.

-> Since BIGACE 2.1.

## Attributes


*  **name** - (optional, string)
    The name of the directory to return.

*  **assign** - (optional, string)
    The name of the variable, the directory will be assigned to. If given, no value will be returned, only the variable is set.


## List of possible "names"

This is a (uncomplete) list of values for the **name** attribute with their descripton.


*  **public** - points to /public/

*  **addon_web** - points to /addon/

The default value (if no **name** parameter is used) will return the directory [/public/cid{CID}/](cid_cid) as absolute URL.

## Example

For all examples we assume:


*  Community ID: 1

*  Domain: www.example.com

*  Installed in the subdirectory: cms/

### Example 1

This example displays the Image "foo.jpg" from the Communitys public subdirectory "bar":

	:::html
	`<img src="{directory}bar/foo.jpg" alt="" />`

What would create the URL: **http://www.example.com/cms/public/cid1/bar/foo.jpg**.

### Example 2

The next example displays the Image "foo.jpg" from the public directory:

	:::html
	`<img src="{directory name="public"}foo.jpg" alt="" />`

This creates the URL: **http://www.example.com/cms/public/foo.jpg**.

