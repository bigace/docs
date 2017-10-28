# Smileys

The Smiley extension is a helper package to parse any kind of Strings, to replace textual smileys like ;) into something like ;-)

The textual smileys will be replaced by working HTML `<img src="/path/smiley.gif">` TAGs.

`<WRAP center round download>`

Get all downloads from:

[Smileys detail page](http://www.bigace.de/plugins/detail/31-Smileys)

`</WRAP>`

## Usage

Install and then apply the Smarty modifier **smileys** to any String you like to be smiley'fied.

If you write your own module, you can simply include the Smiley class:

	:::php
	import('classes.parser.Smileys');

and then parse a String:

	:::php
	$code = "A Hello World :) with a Big Band :band:";
	$smileys = Smileys::parseCode($code, false);


The second parameter indicates whether we parse only default Smileys like **;)** or even extended Smileys like **:lol:** or **:hbd:**.

## Smarty modifier

The Smiley Plugin uses a Smarty modifier for easy Template usage.

Please visit its page for further information:

*  [{";)"](smarty_tags/smileys) - parse an input string to replace inherited smileys with icons

## Included smileys

A small script is included, which lists all existing smileys with the replacer strings.
You find it at **/addon/smileys/index.php**. 

Open it with http://yourdomain/pathToBigace/addon/smileys/index.php.

