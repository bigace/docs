# Using Smarty in external applications

This short tutorial should demonstrate, how to use Smarty and even your own design in external applications.
You could also use this demonstration, to display the BIGACE error pages in your site-wide design.

## BIGACE environment

The first thing you have to do, is to initialize a proper BIGACE environment. This is done by including the PHP script **/system/libs/init_session.inc.php**:

`<codephp >`require_once(PATH-TO-BIGACE."/system/libs/init_session.inc.php");`</code>`

__Note:__ If you are already in a valid BIGACE context, like a module, a php template or an BIGACE error page, you do not need to include the file!

## Initialize Smarty

You have to load the BIGACE implementation for Smarty and load the template. Then display this template, using the Smarty engine:

	:::php
	import('classes.smarty.BigaceSmarty');
	import('classes.smarty.SmartyTemplate');
	$tpl = new SmartyTemplate("TemplateName");
	$smarty = BigaceSmarty::getSmarty();
	$smarty->display($tpl->getFilename());


As simple as that?!? Yes, almost... The "problem" is, that most templates use some of the global variables like **$MENU**, and in this case, these variables do not exist. So, if you experience problems with the above method, check your logfile for the missing variables and add them to the Smarty context:

	:::php
	import('classes.smarty.BigaceSmarty');
	import('classes.smarty.SmartyTemplate');
	import('classes.menu.MenuService');
	
	$MENU_SERVICE = new MenuService();
	$MENU = $MENU_SERVICE->getMenu( _BIGACE_TOP_LEVEL, _ULC_ ); // top level is the root page, _ULC_ is the current context language
	
	$tpl = new SmartyTemplate("TemplateName");
	$smarty = BigaceSmarty::getSmarty();
	$smarty->assign('MENU', $MENU);
	$smarty->display($tpl->getFilename());


__Note:__ Replace "TemplateName" with the name of your template as seen in the administration.


## Example

Lets say, you want to use the template "BLIX" (find the template name in your Administration):

{{bigace:tutorial:template-name.png|How to find the name of the template}}

And with "BLIX" you want to display the page "Test" which has the ID "2" in "english". We further assume, that you run the file outside any BIGACE context from the BIGACE Root. Then you would do something like this:

	:::php
	require_once(dirname(__FILE__)."/system/libs/init_session.inc.php");
	
	// import required classes
	import('classes.smarty.BigaceSmarty');
	import('classes.smarty.SmartyTemplate');
	import('classes.menu.MenuService');
	import('classes.language.Language');
	
	// initialize language from context
	$LANGUAGE = new Language(_ULC_);
	// make sure you use the correct encoding - mostly UTF-8
	header( "Content-Type:text/html; charset=" . $LANGUAGE->getCharset() );
	
	// fetch the meu to be displayed
	$MENU_SERVICE = new MenuService();
	$MENU = $MENU_SERVICE->getMenu(2, "en");
	// load the template
	$tpl = new SmartyTemplate("BLIX");
	// create the smarty context
	$smarty = BigaceSmarty::getSmarty();
	$smarty->assign('MENU', $MENU);
	// and display the template
	$smarty->display($tpl->getFilename());

