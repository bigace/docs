# Building BIGACE

## ANT Build File

BIGACE uses an ANT Build File to automate the several Build tasks.

It is only available in [subversion](subversion) and does not come with the released Files.

## Build Properties

The ANT Build File only works when the Build Properties File is customized to fit to your System.

You have to adjust Path and Files to point to your local sources!


## 3rd Party Software

BIGACE uses a lot of other OpenSource Components to fulfil several Tasks.

These Packages are all available for free and need to be placed on the building Computer.
You also have to correct the path within the Build Properties, to point to your HDD.


*  AdoDB - [http://adodb.sourceforge.net/](http://adodb.sourceforge.net/)

*  Smarty - [http://www.smarty.net/](http://www.smarty.net/)

*  FCKeditor - [http://www.fckeditor.net](http://www.fckeditor.net)

*  b2evo Captcha - [http://b2evo-captcha.sourceforge.net/](http://b2evo-captcha.sourceforge.net/)

*  TinyMCE (for TinyMCE Extension) - [http://tinymce.moxiecode.com/](http://tinymce.moxiecode.com/)

The used version of each package can be found at the BIGACE Credit Screen (in your BIGACE Administration).

## Documentation (deprecated!)

The old Documentation of BIGACE (up to version 2.0) is written in Docbook. In this way it was possible to generate many different Documentation Formats (HTML, chunked HTML, PDF).
But time changes and the documentation is now be written with BIGACE (see Forum discussion).

There are some ANT XSLT tasks available to generate the Documentation, but you might also generate them with Java Command Line tools or any other XSLT Engine... For a documentation about these tasks have a look at Google and at "DocBook: The Definitive Guide".

Software required for generating the Documentations:

    * docbook-xsl-1.69.1 (XSL Stylesheets)
    * docbook-xml-4.2 (DTD)
    * saxon.jar (XML/XSL Engine - Saxon 6.5.5)
    * resolver.jar (from Apache: xml-commons-resolver-1.1 - needed for Ant XSL Task to find catalog files!)
    * Java 1.5 (couldn't make it run with 1.4)

If the Build File Solution with Catalog Files does not work, you have to adjust the file locations to the XSL Stylesheets (to point to your drive).

Adjust the following files:

    * /DOCU/MANUAL/developer/manual.xml
    * /DOCU/MANUAL/manual/manual.xml
    * /DOCU/MANUAL/xsl/style*.xsl

If you do not want the XSL Engine to load the DTD each time from the Internet, you also have to adjust the Build Properties File to point to the Docbook Catalog XML File.

Some links that might be useful:

    * [http://sagehill.net/docbookxsl/index.html](http://sagehill.net/docbookxsl/index.html)
    * [http://docbook.sourceforge.net/](http://docbook.sourceforge.net/)
    * [http://richard.cyganiak.de/2003/xml/oeb_docbook/index.html](http://richard.cyganiak.de/2003/xml/oeb_docbook/index.html)
    * [http://www.goshaky.com/docbook-tutorial/](http://www.goshaky.com/docbook-tutorial/)

