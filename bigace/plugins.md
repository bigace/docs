# Plugin

*How to build your first Bigace Plugin.*

**This page is a draft version, we apologize for that! Please ask in the forum for further information. You can also have a look into the API of the [Bigace_Hooks class](http://dev.bigace.org/api/latest/Bigace/Bigace_Hooks.html).**

BIGACE 2.5 introduced a new Plugin framework, which gives you the abbility to create your own CMS extensions - to hook into the core system without code modification.

There are two different ways of hooking into the system, one is to modify data (by a so called **Filter**), which is there to manipulate the results. The other way is to register an **Action**, which is executed when the system sends the signal.

We will provide you with more information soon, in the meanwhile, we give you a list of all available signals you can hook on.

Register your Plugin methods at the static class "Hooks" by calling:

	:::php
	Hooks::add_filter('event_name_to_hook_on', 'function_name_to_execute', importance, params_count);
	Hooks::add_action('event_name_to_hook_on', 'function_name_to_execute', importance, params_count);


If you need further events or filter, let us know in the feature request forum. We will add it to the BIGACE core.

## Plugin files

Create a new PHP file below the /plugins/ directory and add this minimal code to it:

	:::php
	<?php
	/*
	Plugin Name: My plugin
	Plugin URI: http://www.example.com/plugin
	Description: This plugins does something useful.
	Author: Developer name
	Version: 0.1
	Author URI: http://www.example.com/

	*/
	?>


After you added this header, your plugin will be available in the plugins tab of your extension administration. Activate it and it (the file) will be loaded on BIGACE startup. 

Hook into the system with [filters and actions](bigace/developer/hooks) and execute any code you like!

