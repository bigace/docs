# FirePHP

Debugging Server-side applications can be a time-consuming task and I guess all PHP developer know this frustrating search for bugs, using "raw" debug messages like:

	:::php
	echo "`<br>`1";
	print_r($myArray)
	...


Thanks to the great Firebug extension for Firefox, a lot of web-development tasks have become easier. 
Now, its getting even better! Introducing the [FirePHP](http://www.firephp.org/) extension for BIGACE lets you send all BIGACE and PHP related log messages to the
Firebug console.


`<WRAP center round download>`

Get all downloads from:

[FirePHP detail page](http://www.bigace.de/plugins/detail/36-FirePHP)

`</WRAP>`

## Installation

 1.  Install [Firefox](http://www.mozilla.com/firefox/) (blame you, if you don't already have it LOL)
 2.  Install the [Firebug](https///addons.mozilla.org/firefox/addon/1843) addon
 3.  Install the [FirePHP](https///addons.mozilla.org/firefox/addon/6149) addon
 4.  Install the BIGACE FirePHP Plugin (download link above)
 5.  Follow configuration info, see below

## Configuration of the FirePHP Plugin for BIGACE

Read how to [configure the logger class](developer/logger).
After configuration and reloading the page you will find your log messages in the console like this:

{{bigace:extensions:development:example-log.png|Screenshot of some example log messages}}

## Usage in your modules

If you develop your own modules or other BIGACE extensions, you can use the following PHP code to log messages:

	:::php
	$GLOBALS['LOGGER']->logError('This is a simple test to demonstrate a FirePHP error');
	$GLOBALS['LOGGER']->logInfo('A demonstration of a FirePHP warning');
	$GLOBALS['LOGGER']->logDebug('Another message, to demonstrate a FirePHP info');


Or you use one of the FirePHP constants for logging directly:

	:::php
	$GLOBALS['LOGGER']->log(FirePHP::TRACE, 'The Trace level is mega useful!');


This is the result of the TRACE log:

{{bigace:extensions:development:trace-log.png|A trace log message logs the complete backtrace}}

Obviously, you can read it better in the console than in that resized screenshot ;)

And here are all available log levels:

	:::php
	class FirePHP {
	
	  const LOG = 'LOG';
	  const INFO = 'INFO';
	  const WARN = 'WARN';
	  const ERROR = 'ERROR';
	  const DUMP = 'DUMP';
	  const TRACE = 'TRACE';
	  const EXCEPTION = 'EXCEPTION';
	  const TABLE = 'TABLE';
	  ...
	}


There are many more options available, please refer to the [official QuickStart](http://www.firephp.org/Wiki/Main/QuickStart) docu.


## FirePHP Homepage

If you are interested in more information about [FirePHP](http://www.firephp.org/), please visit their homepage at [http://www.firephp.org/](http://www.firephp.org/).

A great framework, thanks to its developer [Christoph Dorn](http://www.christophdorn.com/).
Oh and BTW, **FirePHP** is licensed with "New BSD License".
