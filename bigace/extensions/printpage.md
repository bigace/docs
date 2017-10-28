# Print Page

This extension needs BIGACE 2.5. 

If you are running a BIGACE 2.5 RC 4 or earlier, you have to apply a tiny patch. Please read [this forum thread](http://forum.bigace.de/feature-requests/(1984503-)-printer-friendly-pages/) to know how.

## Downloads


*  [Version 0.1](http://downloads.sourceforge.net/bigace/PrintPage_0.1.zip) for BIGACE 2.5 (12 March 2009)


## Installation


*  Install the archive

*  Edit your template and add the following code:

	:::html
	    `<script type="text/javascript">`
	    <!--{literal}
	    function printPage() {
	       {/literal}
	       fenster = open("{link_print item=$MENU}","ModulAdmin","menubar=no,toolbar=no,statusbar=no,directories=no,location=no,scrollbars=yes,resizable=no,height=600,width=800,screenX=0,screenY=0");
	       bBreite=screen.width;
	       bHoehe=screen.height;
	       fenster.moveTo((bBreite-800)/2,(bHoehe-600)/2);
	       {literal}
	    }
	    {/literal}// -->
	    `</script>`
	    `<a href="{link_print item=$MENU}" target="_blank" onclick="printPage(); return false;" rel="nofollow">`Print page`</a>`


## Customization

If you do not like the final output of your "print page", you can either edit:

*  the print template "PRINT-PAGE"

*  or the print stylesheet "Print-Page"

