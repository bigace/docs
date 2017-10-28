# Zend Framework

NOTE: This docu is outdated with Bigace 3, as Bigace 3 is build on top of the Zend Framework and the classes are in the PHP include_path.

The Zend Framework is a powerful package of PHP classes, which can boost your development time.

If you want to use the ZF in BIGACE v2.x, you have to do three simple steps:

 1.  Download the latest package
 2.  Extract it to your BIGACE addon/ folder
 3.  Customize the Include path

## Download the latest package

Zend offers two packages, the Full and the Minimal package. I recommend starting with the Minimal package, but it depends on your needs.

Get them from the [Zend Download](http://framework.zend.com/download/current/) pages.

## Extract it to your addon/ folder

After downloading you have to extract the package and upload it to the **/addon/** folder.

You need to have the following directory structure after uploading:

	
	/addon/ZendFramework/library/Zend/...


Where **...** is the folder where the Zend base classes like **Loader.php** and all the class subdirectories are located.

## Customize the Include path

In order for the Zend Framework to work properly, you have to change the Include path, so the Zend Loader can find the classes.

The common way is to set the include path in your script, which uses the Zend API.

	:::php
	set_include_path(get_include_path() . PATH_SEPARATOR . _BIGACE_DIR_ADDON . 'ZendFramework/library');


To load a Zend class, you would call:

	:::php
	set_include_path(get_include_path() . PATH_SEPARATOR . _BIGACE_DIR_ADDON . 'ZendFramework/library');
	require_once('Zend/Loader.php');
	Zend_Loader::loadClass('Zend_Gdata');`</code>`
	
	