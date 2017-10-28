# credits

The credits [filter](bigace/developer/hooks) will be executed before the [bigace:manual:about](bigace/manual/about) screen will be rendered.

It holds an array of credit entries.


## Example usage

	:::php
	Hooks::add_filter('credits', 'getAdminCredits', 10, 1);
	
	function getAdminCredits(array $credits)
	{
	    $credits['Foo'] = array(
	        'Foo' => array(
	            'title' => 'foo',
	            'weblink' => "http://wiki.bigace.de/bigace:extensions:foo",
	            'copyright' => "Kevin Papst",
	            'description' => "Foo is a plugin to demonstrate the 'credits' filter."
	        )
	    );
	    return $credits;
	}


## See also


*  You can also create an INI file to display [bigace:developer:credits](bigace/developer/credits).

*  [bigace:developer:hooks](bigace/developer/hooks)

*  Writing [bigace:plugins](bigace/plugins) to extend Bigace

