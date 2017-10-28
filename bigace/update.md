# Updates

If you want to develop your own [Extension](extensions) for BIGACE (like your own template, admin panel or a module), you should use the "Update System", which enables you to use the full power of automatic SQL, XML and file deployment.

**The module auto-creator**

If you develop a module, try the [module auto-creator](http://dev.bigace-cms.com/Module-Creator), you can download a module with the most important files pre-filled.

**The manual way**

The following will show you, how to create a module manually.

## update.ini

	:::ini
	[info]
	version = "`<Plugin_Version>`"
	title = "`<Name_of_the_Pugin>`"
	description = "`<A_longer_description>`"
	readme = "`<Name_of_Readme_file>`"
	; for example update.html
	  
	[includes]
	1 = `<Filename_that_will_be_included>`
	; list as many includes you may need
	; Add includes here if you - for example - use Update Classes
	 
	[ignore_files]
	1 = `<Name_of_the_File_that_should_not_be_copied>`
	; `<key>` = `<Filename>`
	; 1 = readme.txt 
	; key = must be unique, any allowed key in an Ini File
	; Filename = Filename should be uniquie within all Update Subfolders
	 
	[system]
	class = `<System_Update_Classname_to_reflect>`
	sql = `<Filename_of_the_System_SQL_to_be_Executed>`
	 
	[consumer]
	class = `<Consumer_Update_Classname_to_reflect>`
	sql = `<Filename_of_the_Consumer_SQL_to_be_Executed>`
	
	[permission]
	consumer = `<All_Consumer_IDs_allowed_to_install_this_Update>`
	; consumer = ALL (all consumer are allowed)
	; consumer = 0,3,4 (all permitted Consumer IDs in a comma separated list
	version = `<The_required_BIGACE_Version_for_this_Update>`
	comparator = "<"
	; the default comparator is ">="
	; see the PHP function version_compare() for possible Comparators
	
	[system_delete]
	xx = `<Filename_to_be_deleted>`
	; 01 = /system/config/notexisting.php
	
	[consumer_delete]
	xx = `<Filename_to_be_deleted>`
	; 01 = "consumer/cid{CID}/presentation/layout/notexisting.php"


## A example Plugin

This shows a minimum modul plugin.

Files:

 1.  update.ini
 2.  consumer/cid{CID}/modul/foo/modul.php
 3.  consumer/cid{CID}/modul/foo/modul.ini

update.ini:

	:::ini
	[info]
	version = "1.0"
	title = "Foo Plugin"
	description = "Some useful information for the end-user"


Now create the ZIP as shown below and install the extension with the Extension administration.

## Create an executable ZIP file

To share your development, you should pack all sources to an compatible ZIP archive.
The used ZIP class supports only special kind of archives, so if you see "Given Archive is not a valid BIGACE Update Archive: foo.zip", you packed it with an incompatible algorithm.

Assuming your sources are in the path:
 1.  ~/myModule/update.ini
 2.  ~/myModule/consumer/...
 3.  ~/myModule/system/...

### Create archive on Linux & Mac

... the following should work on mostly all Linux environments (proved to work on Ubuntu & Debian, Mac OS X - Leopard 10.5.3):

	
	cd ~/myModule/
	zip -X -r -7 /tmp/myModule.zip *


Now you have the deployable ZIP file **myModule.zip** in your /tmp/ folder.

### Create archive on Windows

Using **WinRAR**:

Go to your myModule folder in Windows Explorer and select all files that should be included (I guess all?!), choose "Add to an archive". Now choose "ZIP" in the next GUI and leave "Compression rate" at "normal".
Thats it, the created archive should be compatible.

This is a short translation of [a german forum thread](http://forum.bigace.de/templates/eigenes-design-als-erweiterung/msg3240/#msg3240).
