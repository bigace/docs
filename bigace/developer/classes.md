# Classes

In Bigace 3.0 there are two main class types: the legacy classes and the new classes, which use autoloading and are all prefixed with Bigace_.

To use the new class type, simply instantiate the class, call the static method or class constant you want:

	:::php
	$config = Bigace_Config::get("system", "hide.footer");
	$exception = new Bigace_Exception('A dummy exception');
	$version = Bigace_Core::VERSION;


You don't need to include these classes(!), there is an registered autoloader namespace for them.

**Note:** Try to avoid the usage of the legacy API, as it might change between the next minor versions. The plan is, to completely remove the legacy code or migrate it to the new prefixed namespace. If you use it, read the changelogs carefully!
We CANNOT guarantee backward compatibility for the legacy API from 3.0 on.

## Bigace 2.x (legacy API)

In Bigace 2.x two main packages were available: “api” and “classes”.

The "api" folder holds interface definitions (due to PHP4 compatibility they are still classes, but meant as interfaces), the "class" folder is the place to find implementations of these interfaces and all core classes.

## Loading Classes

To load a class, you type something like this:

	:::php
	import('package.subpackage.classname');


Package here is "api" or "classes". Subpackage is the path beneath the Package, for example "item" or "util/links".
Sach folder separator (/) has to be replaced by a (.) dot.

For example, you want to load the Class "system/util/links/SearchLink.php", you type

	:::php
	import('classes.util.links.SearchLink');


The import function uses Java naming syntax, what makes it possible to load subpackages within any directory depth.

All Classes that come shipped with BIGACE use Java Naming Syntax, what at least means Filename.php = Classname.

Some further examples of loading Classes:

	:::php
	import('api.principal.Principal');
	import('classes.principal.DefaultPrincipal');
	import('classes.item.Item');
	import('classes.util.links.SearchLink');


