# Modules

For creating a new Modul, at least the following Folder and File structure is required:

	
	--- /consumer/cid{CID}/modul/
	   |
	   +--- /modulName/
	      |
	      +-------- modul.php


Read more about the path [/consumer/cid{CID}/](cid_cid). Assume Community ID 1, you place your module in **/consumer/cid1/modul/**.

If you added the folder correctly, you should be able to use this module for menu pages.

If your module uses extended features like translations, then you should create the following structure:

	
	--- /consumer/cid{CID}/modul/
	   |
	   +--- /modulName/
	      |
	      +-------- modul.php
	      +-------- modul.ini
	      |
	      +-------- /translation/
	      |       | 
	      |       +-------- /en/
	      |       |       |
	      |       |       +-------- modulName.properties
	      |       | 
	      |       +-------- /../
	      |               |
	      |               +-------- modulName.properties


Follow the naming syntax and case, otherwise your module will likely not work.

Read the section "[Translations](Translations)" for knowledge about how BIGACE handles translations.

## modul.php

This is the main Modul File that holds the full Modules logic. Simply script your PHP code as you always do.

## modul.ini

This is the Modul Configuration File, that could look like this:

	
	;
	; Example INI File for the Developer Manual
	;
	
	; possible settings are TRUE and FALSE
	translate = FALSE
	; a comma separated list of functional right names
	frights =
	
	; following is optional and only required if your modul uses Modul Configurations
	; it is a comma separated list of property name (avoid special character)
	properties = "property_foo,property_bar"
	
	[property_foo]
	; shown in the modul config dialog as title
	name = "Foo will be used?"
	; the type. available: "Boolean", "String", "Integer", "Text", "Category"
	type = "Boolean"
	; whether this value must be set for proper modul work - the value is currently NOT tested by the application!
	; you should avoid setting to "false" unless you cannot apply default values (like email address)
	optional = true
	; the default value, if the configuration is not set
	default = false
	
	[property_bar]
	name = "An example value"
	type = "Text"
	optional = true
	default = "A default values, which will be used as long as the user did not set on"


If you switch "translate" to "TRUE", the optional Translation File "translation.lang.php - translation.properties" will be loaded into the global Translation Namespace.

Please note: If you want to use settings, then you should declare at least one functional permission string like this:

	
	frights = system_admin

Now every logged in user linked to a user group that owns the permission "system_admin" will be able to edit [bigace:developer:v2:module_admin](developer/v2/module_admin).
## modul.properties

This File holds the description and name for the Modul and needs only 3 lines:

	
	 ; a comment
	 name = the modules name
	 title = the modules title
	 description = a short description of this module


The “Name” is shown in the Menu Administration, the “Title” and “Description” will be shown in the Module Admin Plugin.

These translations are not accessible within the Global Namespace, but only through the modules class-methods:

	:::php
	$module = new Module("x");
	$name   = $module->getName();
	echo "Translated name for Module x is: " . $name;



## translation.properties

Want to use translations in your modules output? Then create the file translation.properties in the correct language folder (see above) and switch the INI setting "translate" to "TRUE". The translations will then be auto-loaded.

### Links

More about modules:

*  [bigace:developer:v2:module_admin](developer/v2/module_admin) - open module settings dialog and read settings within your module

*  [bigace:developer:v2:module_content](developer/v2/module_content) - how to display page content in your module with PHP

