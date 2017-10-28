# BIGACE with LightHTTPD

BIGACE was originally designed for Apache. Out of the Box, BIGACE only support Apache Rewrite Rules, so if you want to use BIGACE [URL Rewriting](bigace/administration/urlrewriting) feature with [LightHTTPD](bigace/administration/lighthttpd) you have to apply some manual changes.

Thanks to [Gizmor](http://www.gizmor.org/) for this code!

**Requirements:**

*  LightHTTPD Version 1.5 (should work with 1.4.X as well, but untested)

*  Activate mod_magnet/mod_rewrite

*  Server compiled with LUA Support


Copy the following Code to your VirtualHost config:

	
	url.rewrite-once = (
		#If a full URL was given, we rewrite everything
		"^/bigace/(.*?)/(.*?)/(.*?)(?:\?{1}(.*?))?$" => "/public/index.php?cmd=$1&id=$2&name=$3&$4",
							
		#Otherwise this should be a Permalink with a unique URL
		"^/bigace/(.*?)(?:\?{1}(.*?))?$" => "/public/index.php?id=$1&$2"
	)
			
	## If none of the above applied, this was probably a normal filesystem call.
	## But if the file or directory does not exist, treat it as permalink			   
	magnet.attract-physical-path-to = ("/etc/lighttpd/bigace_rewrite.lua")					    


Additionally you need the the following script, which needs to be saved at /etc/lighttpd/bigace_rewrite.lua:

	
	-- Additional Rewrite-Rule for Bigace-CMS (bigace.de) running on Lighttpd
	-- Created by S. Huebener / gizmor.org
	
	-- check if file/folder exists
	function file_exists(path)
		local attr = lighty.stat(path)
		
		if(attr) then return true
		else return false
		end
	end
	
	
	local prefix = '/public'
	local index_file = '/index.php'
	
	if(not file_exists(lighty.env["physical.path"])) then
		-- file/folder not found
	
	    	local filename = string.sub(lighty.env["uri.path"],2) or ""
	    	local query = lighty.env["uri.query"] or ""
	
	    	lighty.env["uri.path"]          = prefix .. index_file
		lighty.env["uri.query"] 		= "id="..filename..(query ~= "" and "&" or "")..query
		lighty.env["physical.rel-path"] = lighty.env["uri.path"]
		lighty.env["request.orig-uri"]  = lighty.env["request.uri"]
		lighty.env["physical.path"]     = lighty.env["physical.doc-root"] .. lighty.env["physical.rel-path"]
	end


Note: If you change the filename, you need to change the name in your VirtualHost config as well!
