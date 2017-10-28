Links of interest:

   * [URL Rewriting](bigace/administration/urlrewriting) via .htaccess files
   * Using [SSL](bigace/administration/ssl) encryption
   * [Password salting](bigace/administration/salting) to fight dictionary attacks

# Security

Make sure, that ONLY the files in the folder:
 1.  **./** 
 2.  **./addon/**
 3.  **./public/** 
are accessible from outside (via Webserver).

In other words the folder:

 1.  **/consumer/**
 2.  **/misc/**
 3.  **/system/**

need our attention.

To make sure none of these folders (and files) can be read by a Browser, there are several ways. 

## htaccess

One solution (supported by the BIGACE Installer) is to use **.htaccess** files.

Place them in the mentioned folders:

    * **/consumer/**
    * **/misc/**
    * **/system/**

Add the following code to the **.htaccess** files:

	:::ini
	deny from all


**Tip:**
The required **.htaccess** files come with BIGACE and can automatically be placed at the correct locations when installing, choosing the option "Usage of Rewrite engine allowed".

**Note:**
If you use .htaccess files and the Webserver denies its usage, you might encounter "System error" pages.


## Directory permission

The other way could be to change the file and folder permission, to make sure they cannot be accessed from outside. 
As long as this depends on your hosting environment, you should test it. 

Try this:

	
	sudo chmod -R 644 /var/www/wherever
	sudo chmod -R +X /var/www/wherever

