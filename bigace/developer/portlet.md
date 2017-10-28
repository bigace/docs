# Portlets

This article covers a basic introduction into the Portlet System.

Please have a look at the [Portlet API](http://bigace.sourceforge.net/phpdoc/2.4/bigace-api/portlet/Portlet.html) for the PHP part.

## Create a portlet (basic)


*  Go to **/system/classes/portlets/**

*  Copy one of the existing files, rename it 

*  Open the file and rename the PHP class inside accordingly

*  Change the display name - see method getTitle()

*  Save the new file

*  Reload the Portlet Administration, the Portlet should be visible

## Installation

New portlets will be available once they are saved in the folder **/system/classes/portlets/**. 

## Create a portlet (advanced)

This is a tutorial in writing Bigace portlets.

We start with a simple "Hello World" portlet, which we will step-by-step build up to a complex version with more functionality.

### The theory

Portlets are PHP Classes which extend the base "Portlet" class, located at **/system/api/portlet/Portlet.php**.
These Portlet source files are located at **/system/classes/portlets/** where they will be found automatically 
and displayed in the Portlet Administration.

Portlets need to implement at least two functions (with 2.5 one ins enough, **getTitle()** can be skipped there):

 1.  **getTitle()** - returning the title of the Portlet, displayed in Portlet Administration
 2.  **getHtml()** - returning the HTML output of your Portlet

Depending on your template, the portlets title might be displayed there as well.

I guess you don't even have to have small experience with OO programming, because creating your own portlets is an easy task. If you don't understand whats going on here, please ask us in the forum.

### The practice

Create the file **/system/classes/portlets/HelloWorld.php** and copy the following code into the empty file:

	:::php
	<?php
	
	import('api.portlet.Portlet');
	
	class HelloWorld extends Portlet
	{
	    function getTitle() {
	        return "Hello World";
	    }
	    function getHtml() {
	        return "`<h1>`Hello World!`</h1>`";
	    }
	}
	
	?>


So, what happens? The **import()** loads the base class to make sure you can extend Portlet.
The class itself is defined and the two methods **getTitle()** and **getHtml()**, as discussed before, 
are overwritten. 
There are more functions available, we will use them later.

For now, save the file, open your Portlet Administration and you will see a new entry:

{{bigace:tutorial:portlet-new-entry.png|The new portlet is shown in the list of available Portlets}}

As you can see, there are no configurations available for this portlet. 
This will change if we add a class constructor, where we set a portlet parameter:

	:::php
	    function HelloWorld() {
	        $this->setParameter( 'user', 'foo' );
	    }


The portlet now holds a parameter called "user" with the default value "foo". The value could
be empty as well, but in many cases, you will pass some default values to easify the users life.

If you now select HelloWorld in your Portlet Admin, you now see an input field for "user" with "foo" as value:

{{bigace:tutorial:portlet-config.png|First configuration for the new Portlet}}

Now, we add a third parameter, which should be a menu id, so we can create a link to that page.

	:::php
	    function HelloWorld() {
	        $this->setParameter( 'user', 'foo' );
	        $this->setParameter( 'menuid', '' );
	    }


{{bigace:tutorial:parameter-type.png|Two input fields for the parameter}}

But having an input field for a menu id is not that much fun. Thats where the parameter type comes up.
By default, every parameter is treated as string, but we can change that for every parameter.
We need to overwrite the method **getParameterType($key)** and return the proper type for the given
parameter:

	:::php
	    function getParameterType($key) {
	        switch($key) {
	            case 'menuid':
	                return PORTLET_TYPE_MENUID;
	            default:
	                return PORTLET_TYPE_STRING;
	        }
	    }


So, where are we now?!
We have these two configs, where we change the type of one of them to an interactive element, 
with a menu chooser popup:

{{bigace:tutorial:parameter-type-popup.png|The parameter type changed}}

We are not ready yet, we want to customize the parameter name, to make sure everybody understands their meaning.
To achieve this, we can overwrite the method **getParameterName($key)** to return a String for each parameter:

	:::php
	    function getParameterName($key) {
	        switch($key) {
	            case 'user':
	                return 'Username';
	            case 'menuid':
	                return 'Link target';
	        }
	    }


{{bigace:tutorial:parameter-name.png|Changed names of the parameters}}

Okay, we have two parameter with proper names and and type. But we want to use them as well, so we 
change the **getHtml()** function a bit.
We need the MenuService to load a menu and the LinkHelper tp create a valid link, so we have to add 
two imports as well (add them to the beginning of the file):

	:::php
	    import('classes.util.LinkHelper');
	    import('classes.menu.MenuService');
	
	    function getHtml() {
	        $ms = new MenuService();
	        $menuID = $this->getParameter('menuid');
	        $linkMenu = $ms->getMenu($menuID);
	        $url = LinkHelper::getUrlFromCMSLink(LinkHelper::getCMSLinkFromItem( $linkMenu ));
	
	        return 'Hello World, says `<b>`.$this->getParameter('user').`</b>`!
	                `<br/>`
	                He recommends `<a href="'.$url.'">`.$linkMenu->getName().`</a>`.';
	    }


Almost done! Configure the portlet with some real-life data:

{{bigace:tutorial:helloworld-configured.png|Configured the Portlet with real-life values}}

After adding it to the list of page portlets (don't forget to save) you can reload the page. If you made no Copy&Paste mistake, you will see something like this (if you use the BLIX design):

{{bigace:tutorial:html-output.png|The rendered output of your new Portlet}}

And here is the complete source code for this portlet:

	:::php
	<?php
	
	import('api.portlet.Portlet');
	import('classes.util.LinkHelper');
	import('classes.menu.MenuService');
	
	/**

	 * An example portlet for the BIGACE Web CMS. 
	 * Read the full tutorial at http://wiki.bigace.de/bigace:tutorial:portlet
	 */
	class HelloWorld extends Portlet
	{
	    function HelloWorld() {
	        $this->setParameter( 'user', 'foo' );
	        $this->setParameter( 'menuid', '' );
	    }
	
	    /** 

	     * The title of this portlet.
	     */
	    function getTitle() {
	        return "Hello World";
	    }
	
	    /** 

	     * The HTML, which is returned by this portlet.
	     */
	    function getHtml() {
	        $ms = new MenuService();
	        $menuID = $this->getParameter('menuid');
	        $linkMenu = $ms->getMenu($menuID);
	        $url = LinkHelper::getUrlFromCMSLink(LinkHelper::getCMSLinkFromItem( $linkMenu ));
	
	        return 'Hello World, says `<b>`.$this->getParameter('user').`</b>`!
	                `<br/>`
	                He recommends `<a href="'.$url.'">`.$linkMenu->getName().`</a>`.';
	    }
	
	    /** 

	     * Returns a proper type for each parameter.
	     */
	    function getParameterType($key) {
	        switch($key) {
	            case 'menuid':
	                return PORTLET_TYPE_MENUID;
	            default:
	                return PORTLET_TYPE_STRING;
	        }
	    }
	
	    /** 

	     * Returns a human readable name for each parameter.
	     */
	    function getParameterName($key) {
	        switch($key) {
	            case 'user':
	                return 'Username';
	            case 'menuid':
	                return 'Link target';
	        }
	    }
	}
	
	?>



### Portlet parameter names

Make sure, ever parameter has a unique name for this portlet. start with a character a-z or A-Z followed
by a-Z, A-Z and 0-9.

### Portlet parameter types

This is the list of all parameter types for BIGACE 2.4/2.5:


*  PORTLET_TYPE_STRING

*  PORTLET_TYPE_TEXT

*  PORTLET_TYPE_INT

*  PORTLET_TYPE_INT_POSITIVE

*  PORTLET_TYPE_INT_OPTIONAL

*  PORTLET_TYPE_BOOLEAN

*  PORTLET_TYPE_HTML

*  PORTLET_TYPE_MENUID

*  PORTLET_TYPE_MENUID_OPTIONAL

*  PORTLET_TYPE_LANGUAGE

*  PORTLET_TYPE_LANGUAGE_OPTIONAL

Please refer to the Portlet class docu for more information!

### Further links

There is an [old page about Portlets](developer/portlet), with mixed information...

