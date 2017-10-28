# IIS - Using BIGACE with Microsoft Internet Information Services

BIGACE was tested on a IIS 6, successful with activated URL rewriting (but without .htaccess files to secure folder access).

There is a Forum thread regarding the installation, please read it and post your feedback there: [http://forum.bigace.de/general/bigace-2-7-on-a-windows-server/](http://forum.bigace.de/general/bigace-2-7-on-a-windows-server/)

This was tested on an INTRANET server:
I had to give the "Internet Guest" account (IUSR_`<MASHINNAME>`) modify permissions on my C:\inetpub\wwwroot folder

## Installing PHP 5 for IIS 6 

I was following this guide http://peterguy.com/php/install_IIS6.html

This is about version 5.2.6 and uses the "manual" installation.

It requires a ISAPI filter as an dll file named **PHP5ISAPI.DLL** wich are not found in later versions.. i used version 5.2.11

In **PHP.INI** i have these extensions enabled.

	
	extension=php_bz2.dll
	extension=php_curl.dll
	extension=php_exif.dll
	extension=php_gd2.dll
	extension=php_gettext.dll
	extension=php_ldap.dll
	extension=php_mysql.dll
	extension=php_mysqli.dll
	extension=php_openssl.dll
	extension=php_zip.dll


## IIS Rewrite rules

The rules below work with the ISAPI rewrite 3 module from [http://www.helicontech.com/isapi_rewrite/](http://www.helicontech.com/isapi_rewrite/).

The rewrite rules for IIS **ISAPI rewrite 3** are slightly different, so take these:

	
	RewriteEngine On 
	## enabling rewrite.log 
	RewriteLogLevel 9 
	## enabling error.log 
	LogLevel debug 
	
	RewriteBase / 
	
	## Old style URLs, before BIGACE 2.4. Full URLs require complete rewriting 
	RewriteRule ^bigace/([^/]+)/([^/]+)/(.*)$ /public/index.php?cmd=$1&id=$2&name=$3 [NC,QSA] 
	
	## If none of the above applied, this was probably a normal filesystem call. 
	## But if the file or directory does not exist, treat it as permalink 
	RewriteCond %{REQUEST_FILENAME} !-f 
	RewriteCond %{REQUEST_FILENAME} !-d 
	RewriteRule (.*) /public/index.php?id=$1 [QSA] 


You might want to remove the lines "RewriteLogLevel" and "LogLevel" in productive systems, but you will require them for testing and analysis if something doesn't work as expected.
