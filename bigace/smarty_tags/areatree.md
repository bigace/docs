# {areatree}

The {areatree} TAG prints navigation for the current area of the webpage (area = first level below top level)

-> Since BIGACE 2.5.



## Attributes

*  **assign** - (optional, String)
    The name of the template variable the value will be assigned to

*  **language** - (optional, String)
The language to get the tree for, default is the current language from the session (the users language)

*  **css** - (optional,String)
the css class for the rendered link (`<a>`) node, default is empty

*  **hidden** - (optional,boolean)
show also hidden pages in the page tree, defult is false

*  **prefix** - (optional,String)
the html to be prepended to every item link in the areatree (will be printed before the `<a href="...>`itemnam`</a>` code of each item), default is empty

*  **suffix** - (optional,String)
the html to be appended to every item link in the areatree (will be printed after the `<a href="...>`itemnam`</a>` code of each item), default is empty

*  **selected** - (optional,String)
the css class for all items on the path to root, default is empty

*  **start** - (optional,String)
the initial value that will be prepended to the output of this tag, default is empty

*  **maxdepth** - (optional,int)
the maximum level depth to crawl into the page tree. No pages with a higher level value then the speicifed will be displayed in the areatree, default is 999 (all levels)

*  **beforeLevelDown** - (optional,String)
get the text/html that should be place before a level up step source code, default is empty

*  **beforeLevelUp** - (optional,String)
the text/html that should be place before a level down step source code, default is empty

*  **assign** - (optional,String)
if set the output of this tag will be assigned to the variable instead of being printed to the output stream 

*  **folded** - (optional,boolean)
indicates if only the subtree elements on path to root (and their siblings) should be shown or all items in the subtree, default is false (=show all items in subtree)

*  **debug** - (optional,boolean)
If set to true, debug output will be printed out while rendering the areatree, default is false












## Example

This example shows how to create a simple multilevel list representing the current area subtree as you would use it for building a css styled navigation:

	:::html
	`<html>`
	...
	`<body>`
	    `<ul class="subnav">`
	        {areatree folded='true' prefix=`<li>` suffix=`</li>` css="subnav" selected='subnavactive' beforeLevelDown=`<li>``<ul>` beforeLevelUp=`</ul>``</li>`}
	    `</ul>`
	`</body>`
	`</html>`


assuming this page structure:

	
	TOP LEVEL
	 |_ area 1 (current area)
	 |   |
	 |   |_ page1 name
	 |   |     |
	 |   |     |_ page2 name
	 |   |     |    |
	 |   |     |    |_page3 name (lets assume this is the current page the user is on)
	 |   |     |    |
	 |   |     |    |_page4 name
	 |   |     |
	 |   |     |_ page5 name
	 |   |         |
	 |   |         |_ page5b name (this page will not be displayed, since the folded parameter is set to true and the parent is not on path to root)
	 |   |         |_ page5c name (this page will not be displayed, since the folded parameter is set to true and the parent is not on path to root)
	 |   |
	 |   |_ page6 name
	 |         |
	 |         |_ page6b name (this page will not be displayed, since the folded parameter is set to true and the parent is not on path to root)
	 |
	 |_ area 2 (will not be displayed, since it is not the current area)
	 |...


this is what the resulting html would look like:

	:::html
	`<html>`
	...
	`<body>`
	    `<ul class="subnav">`
	        `<li>`
	            `<a href="http://www.yourdomain.com/page1.html" class="subnavactive subnavactive_areatree_level_0">`page1 name`</a>`
	        `</li>`
	        `<li>`
	            `<ul>`
	                `<li>`
	                    `<a href="http://www.yourdomain.com/page2.html" class="subnavactive subnavactive_areatree_level_1">`page2 name`</a>`
	                `</li>`
	                `<li>`
	                    `<ul>`
	                        `<li>`
	                            `<a href="http://www.yourdomain.com/page3.html" class="subnavactive subnavactive_areatree_level_2">`page3 name`</a>`
	                        `</li>`
	                        `<li>`
	                            `<a href="http://www.yourdomain.com/page4.html" class="subnav subnav_areatree_level_2">`page4 name`</a>`
	                        `</li>`
	                    `</ul>`
	                `</li>`
	                `<li>`
	                    `<a href="http://www.zirbus.de/page5.html" class="subnav subnav_areatree_level_1">`page5 name`</a>`
	                `</li>`
	            `</ul>`
	        `</li>`
	        `<li>`
	            `<a href="http://www.zirbus.de/page6.html" class="subnav subnav_areatree_level_0">`page6 name`</a>`
	        `</li>`
	    `</ul>`
	`</body>`
	`</html>`







## CSS

use the "css" and "selected" attributes to specify the css classes to be applied to the links.

The areatree tag will also add an additional class to each link which is a level (depth) specific class, allowing you to style every levels items in a different way

e.g. if you use "subnav" as the value for the "css" attributes, then every link in level 0 get the following class attribute values: 

`<a href="..." class="subnav subnav_areatree_level_0">`...`</a>`

the schema for the created class attribute value is always as follows:

`<your css class name>` `<your css class name>`_areatree_level_`<the level of the linked item>`

the same applies for the "selected" attribute.

For a better understanding see also the resulting html of the example given above
