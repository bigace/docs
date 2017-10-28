# Logger

Everyone developer works different, especially when it comes to logging. One wants a logfile and tail, another one echoes messages directly on the page.

Bigace ships with a configurable logging adapter. The configuration is done in the file **/system/config/services.ini**.

## Configure the logger class

Open the config file **/system/config/services.ini** and locate the key "logger" in section [services]:

	:::ini
	[services]
	...
	logger = classes.logger.DBLogger


Change that line to your favorite logger class (here FileLogger):

	:::ini
	logger = classes.logger.FileLogger



## A list of available Logger

For a list of shipped logger types have a look at the folder **/system/classes/logger/**. These are the currently existing ones:


*  DBLogger

*  FileLogger

*  NullLogger

*  RuntimeLogger

*  XmlFileLogger

*  StdoutLogger (since Bigace 2.7.8)

*  [bigace:extensions:development:firephp](extensions/development/firephp) (not included in default installation)

## More about logging


*  [bigace:manual:configurations:system:logger.loglevel](manual/configurations/system/logger.loglevel)

*  [bigace:administration:filelogger](administration/filelogger)

*  [bigace:extensions:development:firephp](extensions/development/firephp)

