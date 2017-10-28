# SEO - Search Engine optimization

This extension is a package of tools and Smarty TAGs, meant to easify your life, making BIGACE more search engine friendly.

You should consider, reading the article about [URL Rewriting](bigace/administration/urlrewriting) (really important for SEO) as well!

**__PLEASE NOTE:__**
The current version works, but it has only a small number of functions right now. Please post any thoughts you have about existing and future releases in the forum!


`<WRAP center round download>`

Get all downloads from:

[SEO detail page](http://www.bigace.de/plugins/detail/28-SEO)

`</WRAP>`

## Quick Intro

SEO:

    * Register for Google Analytics to get your ID
    * put [{google_analytics  id='UA-xxxxxx-x'}](bigace/smarty_tags/google_analytics){google_analytics} in your template
    * wait for a day
 
    OR 

    * Use Piwik for user statistics (read [{piwik}](bigace/smarty_tags/piwik) for more information)
    * put [{piwik}](bigace/smarty_tags/piwik) in your template
    * enjoy your "live" tracking data right away

Sitemap:

    * add /plugins/seo/sitemap-v09.php  at your google webmaster sitemap tools
    * wait for a day :-P

Configurable HTML Metatags:


*  After installation, activate the Plugin at Extensions -> Administration -> Plugins

*  Open a page and edit the values (title, author, robots)

*  Create a page and fill in the values for your metatags

*  Use [{metatags}](bigace/smarty_tags/metatags) in your template

## Contents

 1.  Smarty TAGs: 
    - [{google_analytics}](bigace/smarty_tags/google_analytics)
    - [{piwik}](bigace/smarty_tags/piwik)
 2.  Google Sitemap: see below for usage 
 3.  To use Piwik instead of Google Analytics, please read the [{piwik} documentation](bigace/smarty_tags/piwik)

## Google Sitemap

The Sitemap is multi language, so all pages that are NOT hidden can be indexed!

You need a Google Account for using the [Google Webmaster Tools](http://www.google.com/webmasters/tools).

Lets assume you installed BIGACE at http://www.example.com/ then you supply the Sitemap URL **http://www.example.com/plugins/seo/sitemap-v09.php**.

Read more about the XML Sitemap Standard at: [http://www.sitemaps.org/protocol.php](http://www.sitemaps.org/protocol.php)

__Note:__ This format is supported by all the major search engines, you are not bound to Google!

I just mention Google explicit, because here in Germany it's the only Search engine that is really important...

## Sitemap for all major Search Engines

If you use [URL Rewriting](bigace/administration/urlrewriting), you can even go one step further and edit you .htaccess file in the BIGACE root folder: **/.htaccess**

Add the following line:

	
	RewriteRule ^sitemap.xml$ ./plugins/seo/sitemap-v09.php


**/sitemap.xml** is the default place to look for a sitemap, so it should hopefully be found even without explicit registration.

The new Rewrite Rule should be the first in your .htaccess:

	
	RewriteEngine On 
	RewriteRule ^sitemap.xml$ ./plugins/seo/sitemap-v09.php
	# other default rewrite stuff
	# ...


You can also specify your sitemap in your **/robots.txt** with the folowing line:`<code>`
Sitemap: /plugins/seo/sitemap-v09.php
`</code>`

