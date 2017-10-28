# Module settings

This page covers some code snippets regarding Module settings. 
After reading you should be capable of displaying a link to the module settings dialog and to read your modules configuration.

Want to know more about modules in general? Then read [bigace:modules](bigace/modules).

## Show Admin link and fetch configurations

	:::php
	import('classes.modul.ModulService');
	import('classes.modul.Modul');
	
	$modulService = new ModulService();
	$modul = new Modul($MENU->getModulID());
	
	// if the current user is able to configure the modul, display the config link
	if ($modul->isModulAdmin())
	{
	    import('classes.util.links.ModulAdminLink');
	    import('classes.util.LinkHelper');
	
	    $mdl = new ModulAdminLink();
	    $mdl->setItemID($MENU->getID());
	    $mdl->setLanguageID($MENU->getLanguageID());
	
	    ?>
	    `<script type="text/javascript">`
	    <!--
	    function openAdmin()
	    {
	        fenster = open("`<?php echo LinkHelper::getUrlFromCMSLink($mdl); ?>`","ModulAdmin","menubar=no,toolbar=no,statusbar=no,directories=no,location=no,scrollbars=yes,resizable=no,height=350,width=400,screenX=0,screenY=0");
	        bBreite=screen.width;
	        bHoehe=screen.height;
	        fenster.moveTo((bBreite-400)/2,(bHoehe-350)/2);
	    }
	    // -->
	    `</script>`
	    <?php
	
	    echo `<div class="modulAdminLink" align="left">``<a onClick="openAdmin(); return false;" href="'.LinkHelper::getUrlFromCMSLink($mdl).'">`Module Admin`</a>``</div>`;
	}


## Fetch module configurations

	:::php
	import('classes.modul.ModulService');
	import('classes.modul.Modul');
	
	$mService = new ModulService();
	$modul    = new Modul($MENU->getModulID());
	$config   = $mService->getModulProperties($MENU, $modul);
	
	echo `<ul>`;
	foreach($config AS $key => $value) {
	  echo `<li>`Key `<u>`.$key.`</u>` has value: `<b>`.$value.`</b>``</li>`;
	}
	echo `</ul>`;



## Fetch module configurations 2

This example overwrites the default setting for the key "foo" from your modul.ini file with a dynamic value!

	:::php
	import('classes.modul.ModulService');
	import('classes.modul.Modul');
	
	// default values, must not be set, will overwrite ini "default" setting
	$config = array('foo' => 'I am an dynamic default value: ' . date());
	
	$mService = new ModulService();
	$modul    = new Modul($MENU->getModulID());
	$config   = $mService->getModulProperties($MENU, $modul, $config);


