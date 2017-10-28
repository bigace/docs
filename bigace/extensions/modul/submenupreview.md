# Submenu Preview

This module lists all submenus of the current visitied page with their name and description, including an arrow image as link to the pages.


`<WRAP center round download>`

Get all downloads from:

[Submenu-Preview detail page](http://www.bigace.de/plugins/detail/21-Submenu+Preview)

`</WRAP>`

## Configuration

After installation, you can assign the Permission "submenu_preview_admin" to all Usergroups, who are allowed to configure the module settings.

The module settings are saved for each page, so you can configure it on the first page with different settings than on the second page.

If you open the Module Administration Pop-Up, you can change the following settings:


*  **show_hidden** whether hidden menus should be shown or not

*  **content_top** if "true" the pages content will be shown above the page listing

*  **content_bottom** if "true" the pages content will be shown below the page listing

*  **order** a boolean to indicate if the pages show be listed in reverse order

## Screenshot

The listing looks like the following screenshot, if using in the default template.

{{bigace:extensions:modul:screenshot-submenu-preview.png|}}

## CSS

If you want to change the look of the listing, change the CSS settings:

	:::css
	.modulAdminLink{margin-bottom:10px;}
	#preview {}
	#preview h2 a { text-decoration:none; margin-left:5px; border:0px solid transparent; }
	#preview h2 { display:block; background-color:#eeeeee; padding:2px; margin:0px; }
	#preview p { margin:0px; padding:5px 5px 5px 5px; }
	.nextLevelPreview { border:1px solid #cccccc; margin:0 0 10px 0; }


This is also required for the people using BIGACE 2.4, cause the CSS/HTML definitions changed since the 2.4 release.


