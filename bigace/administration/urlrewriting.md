# URL Rewriting

BIGACE supports beauty URLs by using URL Rewriting features for URLs like **/bigace/smarty/-1/index.html**.

Since BIGACE 2.4 we support even unqiue URLs like **/news.html** or **/beispiel.jpg**.

Read more about [.htaccess security](administration/htaccess).

NOTE: BIGACE supports [LightHTTPD](administration/lighthttpd), please see the linked article.

# Requirements

To use URL Rewriting, this feature must be activated in your (Apache) Webserver.
Note: Other webserver like the ISS, Lighttpd and others are known to work with Rewrite rules too, but they where not yet tested.

## Apache

Rewriting URLs in Apache is done through the mod_rewrite module of [Apache 1](http://httpd.apache.org/docs/1.3/mod/mod_rewrite.html) or [Apache 2](http://httpd.apache.org/docs/2.0/mod/mod_rewrite.html). The module is enabled in httpd.conf with the following line (make sure it is not commented out):

	:::apache
	LoadModule rewrite_module modules/mod_rewrite.so


The setup of this module is done through so called rewrite rules which can be either defined directly in the server's main config or in a .htaccess file located in BIGACE's main directory.  BIGACE comes with an **.htaccess** file which contains the needed rewrite rules, but you have to activate it during installation, choosing the option "Usage of Rewrite engine allowed".

.htaccess files are only honored if Apache's main config allows it. Many default Apache installs don't. To enable them try adding the following to the httpd.conf:

	:::apache
	`<Directory /path/to/bigace>`
	  AllowOverride All
	`</Directory>`


Alternatively you may simply specify the rewrite rules (mentioned below) in httpd.conf:

	:::apache
	`<Directory /path/to/bigace>`
	  RewriteEngine on
	  ... rewrite rules here ...
	`</Directory>`


You may have to restart Apache for these changes to work.

Some users reported getting a "403 - Forbidden" Error after enabling the rewrite support. Setting the FollowSymlinks option seems to solve the problem:

	:::apache
	Options +FollowSymlinks
	RewriteEngine on
	
	...etc.


# Changing URL Rewriting

There are several reasons, why you might enable or disable the URL Rewriting features after installation.
For now, you cannot achieve this automatically, but only by manually changing files.
## Activating URL Rewriting

First, create a file **.htaccess** in your BIGACE root dir with the content:

	
	# Restrict editing to logged in and experienced users only!
	
	RewriteEngine On 
	
	## Not all installations will require the following line.  If you do, 
	## change "/bigace" to the path to your bigace directory relative
	## from your document root.
	#RewriteBase /bigace
	
	# If a full URL was given, we rewrite everything
	RewriteRule ^bigace/(.*)/(.*)/(.*) ./public/index.php?cmd=$1&id=$2&name=$3&%{QUERY_STRING} [PT]
	# Otherwise this should be a Permalink with a unique URL
	RewriteRule ^bigace/(.*) ./public/index.php?id=$1&%{QUERY_STRING} [PT]
	
	# If none of the above applied, this was probably a normal filesystem call.
	# But if the file or directory does not exist, treat it as permalink
	RewriteCond %{REQUEST_FILENAME}       !-f
	RewriteCond %{REQUEST_FILENAME}       !-d
	RewriteRule (.*)                      public/index.php?id=$1&%{QUERY_STRING} [PT]


Secondly, edit the file **/system/config/config.system.php** and change from

	:::php
	define ('_BIGACE_URL_REWRITE', 'false');

to 

	:::php
	define ('_BIGACE_URL_REWRITE', 'true');


After activating URL Rewriting, you will get new input field in each page and item admin form, where you can enter the URL for this object.

If you have existing pages with content that links internally, you might want to adjust these links. Unfortunately there is currently no automated way to do this, you have to open each page in the editor and change the links.

## Deactivating URL Rewriting

If you installed with activated rewriting and Apache doesn't allow its use (overwrite settings with htaccess) or the mod_rewrite is not available, you might see:
 1.  a blank/empty page
 2.  500 Internal Server Error

This is not a BIGACE Bug, but a mis-configuration of your webserver.

At first, you have to delete the files:

*  **/.htaccess**

*  **/public/.htaccess**

Then, edit the file **/system/config/config.system.php** and change from

	:::php
	define ('_BIGACE_URL_REWRITE', 'true');

to 

	:::php
	define ('_BIGACE_URL_REWRITE', 'false');

