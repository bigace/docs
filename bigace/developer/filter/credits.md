# credits

The credits [filter](developer/hooks) will be executed before the [bigace:manual:about](manual/about) screen will be rendered.

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


*  You can also create an INI file to display [bigace:developer:credits](developer/credits).

*  [bigace:developer:hooks](developer/hooks)

*  Writing [bigace:plugins](plugins) to extend Bigace

