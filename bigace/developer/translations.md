# Translations

Static Phrases used for example in [Templates](developer/template), [Modules](modules) or Admin Plugins are normally kept in Language Files. We call these Files **ResourceBundle**.

Community dependend ResourceBundle are saved in [/consumer/cid{CID}/language/](cid_cid).

## ResourceBundle File Format

You can provide Language Files in two Formats, where the first one (PHP File) should be faster to load for the PHP engine and the second one (INI File) easier to handle for Translators and better human readable.

The first one is a normal PHP File (with the File extension '.lang.php') formatted like this:

	:::php
	<?php
	// a comment
	$LANG['hello'] = 'Hello';
	$LANG['world'] = 'out there';
	?>


The second one is a INI file (with the File extension '.properties') like this:

	:::ini
	; a comment
	hello = Hello
	world = out there


## Loading ResourceBundle

Lets make an example and take the ResourceBundle with the Name “foo”.

There are several ways of loading this ResourceBundle. The old way of loading Translations would be to call:

	:::php
	Translations::loadGlobal('foo');


Where you can pass optional a second (the Locale to load) and third Parameter (a further directory to scan).

If you do not pass the second Parameter, the Session Language will be used for loading the Language File.

## Order of Translation File lookup

Lets say you called Translations::loadGlobal('foo','en').

Now the ResourceBundle will be searched in the following directorys:

   1. /consumer/cid{CID}/language/en/foo.lang.php
   2. /consumer/cid{CID}/language/en/foo.properties
   3. /consumer/cid{CID}/language/foo.lang.php
   4. /consumer/cid{CID}/language/foo.properties
   5. /consumer/cid{CID}/language/DEFAULTLOCALE/foo.lang.php
   6. /consumer/cid{CID}/language/DEFAULTLOCALE/foo.properties
   7. /system/language/en/foo.lang.php
   8. /system/language/en/foo.properties
   9. /system/language/foo.lang.php
    10. /system/language/foo.properties
    11. /system/language/DEFAULTLOCALE/foo.lang.php
    12. /system/language/DEFAULTLOCALE/foo.properties

DEFAULTLOCALE is here the configured Default Language of your Community. If the first file was found, the lookup will be stopped!

You see, it could be enough to have only one (3,4) translation file. This one is then the Default file and will be used for each requested language.
