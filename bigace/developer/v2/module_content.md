# Page content in module

To display the contant of a regular page or even the current page, you cannot use the syntax you are using in your template. This is becuase modules are plain old PHP and templates are written in Smarty syntax.

So have to use the [Bigace API](developer/phpdoc) to fetch the content.

In a module you have always access to the current page through the global object $MENU, which represents the current page where the module is loaded inside.

The simplest usage then would be to display the content of the current page:

	:::php
	echo $MENU->getContent();


To display the content of a special page, you have to load it first

	:::php
	$header = new Menu(15, ITEM_LOAD_FULL, "de");
	echo $header->getContent();


Or, if the page is existing in only one language:

	:::php
	$header = new Menu(15);
	echo $header->getContent();

