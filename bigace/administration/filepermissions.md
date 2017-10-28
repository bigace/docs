# File permissions

{{page>wiki:templates:incomplete}}


Please read [http://forum.bigace.de/downloads/bigace-fix-file-permissions/](http://forum.bigace.de/downloads/bigace-fix-file-permissions/) in the meantime.


## BIGACE 3


### Linux

We assume that both, the webserver user and group are called www-data. Please adjust them to your needs in the following calls.

#### Installation

Bigace needs proper file permissions to run or even start the installation process. 

If Bigace won't start because of the message:

	
	An error occurred
	BIGACE: 500
	Error: 0 - cache_dir is not writable


then you might need to adjust the Bigace cache directory "/storage/cache/". Do so by executing:
`chown www-data:www-data storage/cache/`

If you see a "Directory- and File Permission" page during the installation, please adjust the permissions of following directories:

	
	chown www-data:www-data application/bigace/i18n/ 	
	chown www-data:www-data sites/ 	
	chown www-data:www-data application/bigace/configs/ 	
	chown www-data:www-data public/ 	
	chown www-data:www-data public/.cache/ 	
	chown www-data:www-data public/jquery/ 	
	chown www-data:www-data public/system/admin/css/ 	
	chown www-data:www-data storage/logging/ 	
	chown www-data:www-data storage/updates/


