# Bigace 3 - a secure Apache setup

The best way to install Bigace 3 is by installing it with the Apaches DocumentRoot pointing to the public/ folder.

This describes the config files and the required settings for a proper and secure setup.

We use www.example.com as domain and /var/www/bigace/ as home directory of this example installation.

## Apache VHost

First the config file for your Apache Virtual-Host in the most simpe way:

	:::ini
	`<VirtualHost *:80>`
	    ServerAdmin webmaster@example.com
	    ServerName www.example.com
	    DocumentRoot /var/www/bigace/public/
	`</VirtualHost>`


Or a bit more complex and improved setup:


	:::ini
	`<VirtualHost *:80>`
	    ServerAdmin webmaster@example.com
	    ServerName www.example.com
	    ServerSignature Off
	
	    DocumentRoot /var/www/bigace/public/
	    php_admin_value open_basedir /var/www/bigace:/tmp/:/usr/share/php/
	    php_admin_value memory_limit 64M
	
	    RewriteEngine On
	    RewriteCond %{HTTP_HOST} !^www.example.com$ [NC]
	    RewriteRule (.*) http://www.example.com$1 [R=301,L]
	`</VirtualHost>`


## Apache Rewrite

The file /public/.htaccess needs these entries:

	:::ini
	RewriteEngine On
	RewriteCond %{REQUEST_FILENAME} -s [OR]
	RewriteCond %{REQUEST_FILENAME} -l [OR]
	RewriteCond %{REQUEST_FILENAME} -d
	RewriteRule ^.*$ - [NC,L]
	RewriteRule ^.*$ index.php [NC,L]


## Bigace configuration

Check that /application/bigace/configs/bigace.php contains the 'rewrite' setting 'true' ...

	:::php
	return array (
	  ...
	  'rewrite' => true
	);


... and your Community setting in /application/bigace/configs/consumer.ini is correct:

	:::ini
	[www.example.com]
	id = 1



## Error search

If you experience errors, try to add the following line to /public/.htaccess

	:::ini
	SetEnv APPLICATION_ENV development


... that it looks like this:

	:::ini
	SetEnv APPLICATION_ENV development
	
	RewriteEngine On
	RewriteCond %{REQUEST_FILENAME} -s [OR]
	RewriteCond %{REQUEST_FILENAME} -l [OR]
	RewriteCond %{REQUEST_FILENAME} -d
	RewriteRule ^.*$ - [NC,L]
	RewriteRule ^.*$ index.php [NC,L]


Now Bigace error pages will display more information.

