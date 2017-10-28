# Core Libraries

If you want to include a Library in your Script, add a code block like this:

	:::php
	include_once($GLOBALS['_BIGACE']['DIR']['libs'].'init_session.inc.php');
	include_once($GLOBALS['_BIGACE']['DIR']['libs'].'footer.inc.php');


These two Libraries might be interesting for you, the other ones are [deprecated](developer/v2/deprecated) or Core Librarys!

## init_session.inc.php

This script creates a valid environment for BIGACE.

You normally do not have to use it, except, you are not in a BIGACE Context. There is only one case when you need it, you are in a script somewhere and want to use the BIGACE API.

Clearly spoken, when using an BIGACE URL like “/bigace/menu/-1/index.php” or “/public/index.php?id=-1&cmd=menu” forget it!

## footer.inc.php

This script prints the invisible BIGACE Web CMS Footer.

It is "invisible" cause all information are wrapped in a HTML Commentar.

Here is an example:

	:::html
	<!--
	
	   Site is running BIGACE 2.1 
	        a PHP based Web CMS for MySQL
	             (C) Kevin Papst (www.bigace.de)
	
	         User ID   : 32
	         Language  : en
	         Community : 4
	         Time      : 0.12587904930115s
	
	-->


Open the Source Code on a normal Menu Page, scroll to the bottom and you will see.

The footer is configurable in many ways, have a look at your System/Configurations.
