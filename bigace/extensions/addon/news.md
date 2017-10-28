# News

The News System is a fully fleged [Extension](bigace/extensions), initially written for BIGACE 2.4.

**Note:** Since BIGACE 2.6 the "News Entry" template includes the comments include if [Comments](bigace/extensions/addon/comments) plugin is loaded

__Key features:__


*  Creating, editing and deleting of News in a new Admin Panel

*  Comes with Templates for "News Home" and "News Entry"

*  Unlimited News Categories

*  Permissions for creating, editing and deleting News; and for managing News Categories

*  Setup language and template once and then ONLY write (easy authoring for none-experienced User)

*  Each News has a title, teaser, image, date, content and optional categories

*  RSS Feed to display the latest Items

*  automatically inserts RSS url in your template (if using [bigace:smarty_tags:metatags](bigace/smarty_tags/metatags))

*  Several [Smarty TAGs](bigace/smarty_tags) to write your own templates and use News wherever you want

`<WRAP center round download>`

Get all downloads from:

[News detail page](http://www.bigace.de/plugins/detail/26-News)

`</WRAP>`

## Installation

 1.  Download (see below) and [install](bigace/manual/updates) the News.zip
 2.  Activate the Plugin
 3.  Go to [User/Permissions](bigace/manual/grouppermission)
 4.  Assign the news.* Permissions to your Administrator account and to all required Usergroups (see below)
 5.  Reload the Administration, you see the new Menu entry "News" below "Menus"
 6.  Configure your News System (see below "Configuration")
 7.  Open Administration/Menu/News and create your first "Hello World" Test News

Now open your News page (as created in "Configuration") and enjoy your posting.

## Permissions

__Names:__
 1.  news / news.edit
 2.  news / news.create
 3.  news / news.delete
 4.  news / news.categories

__Descriptions:__
 1.  Allows to edit existing News entries
 2.  Allows to create News entries
 3.  Allows to delete News entries
 4.  Allows to create new Categories while editing/creating News entries

## Configuration


*  Create the page "News" (News will be created below here) and assign the "News Home" template

*  Create a "News" category (following News Categories will be stored below)

*  Configure your News System at [Configurations](bigace/manual/configurations) with package "news":

__Names:__
 1.  category.id: *choose formerly created category*
 2.  default.language: *choose the language used to create your news*
 3.  root.id: *choose formerly created news page*
 4.  rss.latest.template (**optional**)
 5.  template.news (**optional**)
 6.  unique.name.extension (**optional**)
 7.  unique.name.pattern (**optional**)

__Description:__
 1.  Category ID to create News Categories below. Children of this category can be selected when editing/creating News.
 2.  Language to use for creating News entries. Used by the {news} TAG and for the list of News entries in News Administration.
 3.  Menu ID, where all News will be created below.
 4.  Template used to render the News Feed. If you want to customize it, create a copy of the original template and assign it here. Otherwise leave as is.
 5.  Template Name, which is assigned to each created News.
 6.  The file extension to be used for unique URLs. Only used with activated [URL rewriting](bigace/administration/urlrewriting).
 7.  The unique name pattern for new items, which will be used as prefix for the News entry unique name. The pattern will be piped through stftime, so its easy possible to create a date in the unique name (for example **%Y-%m-%d/** would create News with unique URLs like **2008-04-01/Example-News.html**).  Only used with activated [URL rewriting](bigace/administration/urlrewriting). (**expert option**)


## Smarty TAGs

The News System comes with some specialized Smarty TAGs.

Please visit their page for further information:

*  [{link_news_rss}](bigace/smarty_tags/link_news_rss) - return the URL to the news RSS feed

*  [{news_categories}](bigace/smarty_tags/news_categories) - fetch all News Categories

*  [{news_category}](bigace/smarty_tags/news_category) - fetch all Categories for one News

*  [{news_item}](bigace/smarty_tags/news_item) - load one special News Item

*  [{news}](bigace/smarty_tags/news) - load a list of (categorized) News entries

*  [modifier: news_date](bigace/smarty_tags/news_date) - encodes a timestamp RFC 2822 compatible

## Related extensions

You might be interested in these extensions as well:


*  [Comments](bigace/extensions/addon/comments) - to build a blog like News System

