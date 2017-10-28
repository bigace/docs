# Development environment

{{page>wiki:templates:incomplete}}

How to setup a proper development environment.

# APPLICATION_ENV

The constant APPLICATION_ENV defines the type of system you are currently working on.
Its defaults to 'production' when the value is not detected.

To set this constant, you could edit the file /public/index.php or you simply set the following line into your .htaccess file:

	
	SetEnv APPLICATION_ENV development


Components that make use of the APPLICATION_ENV constant:

*  [bigace:developer:errorpages](developer/errorpages) - show debug information on 'development' systems

*  [bigace:developer:viewhelper:filemerge](developer/viewhelper/filemerge)
