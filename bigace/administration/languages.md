# System Languages

All available languages in BIGACE are configured with INI Files. These files are stored in the directory **/system/language/** (up to Version 1.8.3.x these Files where stored in /system/languages/).

In a default installation you can find:

    * **de.ini** (for german)
    * **en.ini** (for english)

# Available languages


*  English (installed with default system)

*  German (installed with default system)

*  Dutch (available as extension)

*  [Swedish](bigace/extensions/language/se) (available as extension)


# Creating Languages

If you need a language different from the default Languages German and English, you have to create a File and a folder in "/system/language/".
Both, file and folder use the short language locale as perfix, the file has the suffix ".ini".

For example, you want to use the Dutch language, create:

*  /system/language/nl.ini

*  /system/language/nl/

## Language file structure

The language file structure (here in the example the file /system/language/nl.ini) looks like that:

	:::ini
	;
	; Language definition for Dutch
	; Translations for Dutch made by ????
	;
	
	name        	= Dutch
	translation 	= nl
	locale      	= nl
	full        	= nl_NL
	charset     	= ISO-8859-1
	administration 	= true
	
	[translations]
	name_de     	= "Niederländisch"
	name_en     	= Dutch


The [translations] are not required, but they will be used (if available) to show the Language name in several Administration formulars. If the required translation is not available, the **name** is used.

## Translating BIGACE

If you created a new language, you might want to translate BIGACE now to this new language.
The easiest way is to copy all translation files from **/system/language/de/*.ini** and then edit them file by file.
A administration mask is planned for simplifying this translation process.... but currently it has to be done manually.

## Language Flags (Icons)

At last, copy a language icon to the used Admin Style directory. 
For example, using the Standard Admin Style, this would be **/public/system/style/standard/languages/**.

The filename is the **short locale + ".gif"**. 

To use the example from above (Dutch) you need to create the file:

**/public/system/style/standard/languages/nl.gif**

Good Flag icons can be found at [famfamfam.com Flag Icons](http://www.famfamfam.com/lab/icons/flags/), those are used in the Standard Admin Style.
