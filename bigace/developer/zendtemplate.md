# Zend_Layout

A Zend_Layout is the default implementation of a template (there are other template engines like [Smarty](./smarty) available) in Bigace.

It uses the the capabilities of Zend_Layout and has the power of a Zend_View including the Bigace specific [.:viewhelper](./viewhelper).

## Meta information

Bigace uses a comment parser to fetch meta-information about the layout. Therefor you should put a comment like this in your layouts head:

	:::php
	<?php
	/*
	Description: a short description here
	Widgets: sidebar
	Contents: about,address
	Options: css=editor.css

	*/
	?>



*  **Description** is what it says: a short description about the layout, shown in the [Layout Administration](bigace/manual/layout).

*  **Widgets** activates widgets for this layout. Put a comma separated list of widget columns here. If your layout should support widgets, you need to define one or more column names (use alpha-nummerical values only).

*  **Contents** is a comma separated list of additional content area names  (use alpha-nummerical values only). Each layout can use more than the default content on every page (default if **Contents** is not set). These content areas will be editable through the WYSIWYG editor.

*  **Options** is a comma separated list of layout specific options (key and value are separated by an equal sign like foo=bar,foo1=bar1). They can be used to configure some backend behaviours of Bigace. For possible options see below in section "Options".

*  **Path** defines the relative basepath from the community folder below public (e.g. public/cid1/). Makes it possible to map multiple layouts to one folder.

## Thumbnail

You can attach a thumbnail, so end-user get an idea of the layout when looking through the [Layout Administration](bigace/manual/layout). This thumnail has to have the name "screenshot.png" and a width of 250px. Put it into your layouts public path.

If you want to rename the file use the options "screenshot" (see below) or store it in another path (see "Path" setting).

## Options

The "Options:" setting can be used to change some default behaviours and places.
Currently the following keys are supported:


*  screenshot - relative path from the template path (see "Path" setting)

*  css - relative path to a CSS file that will be used in the Editor (see "Path" setting)

*  styles - relative path to a ckeditor styles file (see [ckeditor docu](http://docs.cksource.com/CKEditor_3.x/Developers_Guide/Styles)). Your style-set must be named "bigace".

*  templates - relative path to a ckeditor templates file (see [ckeditor docu](http://docs.cksource.com/CKEditor_3.x/Developers_Guide/Templates)).

## Create your own layout

This Step-by-Step guide explains how to create your own layout using Zend components.

1)
Our layout will be called "easy-fluffy". As Bigace 3 uses naming conventions to calculate (resource) names like CSS path, you need to adapt "easy-fluffy" to your layout name!

2)
We work in the Community 1, so you might need to adapt that as well, if you develop a template for Community 3.

### Create filesystem structure

 1.  Create the file ''/sites/cid1/views/layouts/easy-fluffy.phtml'' and copy your template code inside
 2.  Create the folder ''/public/cid1/easy-fluffy/''
 3.  Create the file ''/public/cid1/easy-fluffy/styles.css''
 4.  Copy all images/javascript files and everything else that needs to be accessible from the browser to ''/public/cid1/easy-fluffy/''

#### Quick setup

Or to make it real quick, you can download {{:bigace:developer:easy-fluffy.zip|EasyFluffy.zip}} and copy the extracted files to the above named locations.

You get a working layout that uses menus, app links, sitename and widgets and should be easy to customize to your own needs.

### Check your Layout

Switch to the [Layout Administration](bigace/manual/layout) and see if your new layout shows up there with name and description.

To test your new layout, set it as default or apply it to a single page and open that page in the browser.

### Preview thumbnail

After your layout is now ready for work, take a screenshot and save it (with a width of 250px) at ''/public/cid1/EasyFluffy/screenshot.png''. This thumbnail will then show up in the [Layout Administration](bigace/manual/layout) beside the layouts name and description.

## Using ViewHelper

To replace static parts of you template with CMS data, you use the available Bigace specific [.:viewhelper](./viewhelper).

You call ViewHelper in the way you would call class methods from within the class.

	:::php
	`<h1>``<?php echo $this->`sitename(); ?>`</h1>`


As your layout is interpreted as PHP file, you can also use plain PHP or the default ViewHelper shipped with the Zend Framework. 

## See also


*  [Zend_View](http://framework.zend.com/manual/en/zend.view.html)

*  [Zend ViewHelper](http://framework.zend.com/manual/en/zend.view.helpers.html)

*  [Zend_Layout Quickstart](http://framework.zend.com/manual/en/zend.layout.quickstart.html)
