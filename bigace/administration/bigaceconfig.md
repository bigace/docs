# Bigace configuration file

The main configuration file for Bigace that configures the following server settings:

*  Database connection

*  SSL Support

*  URL Rewriting

is located at ''application/bigace/config/bigace.php''.

If you accidentally deleted it, you can recreate by pasting the following code inside the file and change the settings to your server environment:

	:::php
	<?php
	return array (
	  'database' => 
	  array (
	    'type' => 'Mysqli',
	    'host' => 'localhost',
	    'name' => 'bigace',
	    'user' => 'username',
	    'pass' => 'password',
	    'prefix' => 'cms_',
	    'charset' => 'utf8',
	  ),
	  'ssl' => false,
	  'rewrite' => true,
	);


Note: It is correct that there is no closing PHP Tag ?> - read [bigace:developer:codeconventions](developer/codeconventions).
