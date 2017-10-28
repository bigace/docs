# Smarty Tags


*  [{addthis_widget_drop}](smarty_tags/addthis_widget_drop) - 

*  [{areatree}](smarty_tags/areatree) - returns an HTML subtree navigation for the current area of a webpage

*  [{array_rand}](smarty_tags/array_rand) - 

*  [{array_shift}](smarty_tags/array_rand) - 

*  [{bigace_copyright}](smarty_tags/bigace_copyright) - returns a formatted and linked BIGACE copyright footer

*  [{bigace_version}](smarty_tags/bigace_version) - displays or returns the BIGACE version

*  [{breadcrumb}](smarty_tags/breadcrumb) - returns an HTML Breadcrumb navigation

*  [{captcha}](smarty_tags/captcha) - create and validate a Captcha image

*  [{configuration}](smarty_tags/configuration) - fetch or cache a Configuration

*  [{content}](smarty_tags/content) - fetch content for a menu

*  [{counter}](smarty_tags/counter)

*  [{cycle}](smarty_tags/cycle)

*  [{directory}](smarty_tags/directory) - returns a directory of the CMS (e.g. to display images)

*  [{hooks_action}](smarty_tags/hooks_action) - 

*  [{hooks_has_action}](smarty_tags/hooks_has_action) - 

*  [{import}](smarty_tags/import) - imports the given class

*  [{is_leaf}](smarty_tags/is_leaf) - returns whether the item has childs or not (leaf)

*  [{is_parent}](smarty_tags/is_parent) - 

*  [{item_category}](smarty_tags/item_category) - returns the linked Categories of an Item

*  [{language}](smarty_tags/language) - 

*  [{languages}](smarty_tags/languages) - 

*  [{last_created_items}](smarty_tags/last_created_items) - last created Items (website or submenu)

*  [{last_edited_items}](smarty_tags/last_edited_items) - last edited Items (website or submenu)

*  [{link_admin}](smarty_tags/link_admin) - the URL to the "Administration Panel"

*  [{link_auth}](smarty_tags/link_auth) - the URL to perform a "login" authentication

*  [{link_editor}](smarty_tags/link_editor) - the URL to open an content Editor

*  [{link_item_languages}](smarty_tags/link_item_languages) - creates links to the available item language version

*  [{link_locale}](smarty_tags/link_locale) - the URL to switch the Session language

*  [{link_login}](smarty_tags/link_login) - the URL to the "Login" formular

*  [{link_logout}](smarty_tags/link_logout) - the URL to perform a logout

*  [{link_password}](smarty_tags/link_password) - 

*  [{link_portletadmin}](smarty_tags/link_portletadmin) -  

*  [{link_register}](smarty_tags/link_register) - the URL to the "Register Account" formular

*  [{link_search}](smarty_tags/link_search) - the URL to the "Search" application

*  [{link}](smarty_tags/link) - creates a link to an Item

*  [{load_categorized_items}](smarty_tags/load_categorized_items) - 

*  [{load_item_childs}](smarty_tags/load_item_childs) - fetches an array of Menu Items from a specified parent

*  [{load_item}](smarty_tags/load_item) - load an Item and assign it to a Smarty variable

*  [{load_translation}](smarty_tags/load_translation) - load a translation file

*  [{metatags}](smarty_tags/metatags) - echo's html metatags for a page

*  [{modul_check}](smarty_tags/modul_check) - checks if a special modul is installed

*  [{modul}](smarty_tags/modul) - load a menus configured Module

*  [{most_visited}](smarty_tags/most_visited) - returns an array of the most visited items

*  [{navigation}](smarty_tags/navigation) - renders the HTML of a Navigation

*  `<del>`[{navilink}](smarty_tags/navilink) - creates the URL to a Menu`</del>` - //deprecated: use [{link}](smarty_tags/link) instead//

*  [{navitree}](smarty_tags/navitree) - 

*  [{permission_editcontent}](smarty_tags/permission_editcontent) - checks if a user is allowed to edit a pages content

*  [{portlet}](smarty_tags/portlet) - fetch one defined portlet

*  [{portlets}](smarty_tags/portlets) - fetch portlets for an Item

*  [{project_field}](smarty_tags/project_field) - 

*  [{random_image}](smarty_tags/random_image) - 

*  [{readdir}](smarty_tags/readdir) - 

*  [{redirect}](smarty_tags/redirect) - sends a redirect header

*  [{sitename}](smarty_tags/sitename) - the configured sitename

*  [{skype_online}](smarty_tags/skype_online) - shows the status of a skype user as image

*  [{stylesheet}](smarty_tags/stylesheet) - fetch a Smarty Stylesheet or its URL

*  [{switch_language}](smarty_tags/switch_language) - renders HTML for diplaying a Language switcher with Flag images

*  [{template}](smarty_tags/template) - assign a Smarty Template or returns its full URL 

*  [{thumbnail}](smarty_tags/thumbnail) - create a URL to display a dynamically created Image thumbnail

*  [{translate}](smarty_tags/translate) - fetches a String from the Translation

*  [{user}](smarty_tags/user) - fetches a User or the Username

**Only for administration templates:**

The following TAGs are only meant for developer who create own admin templates.

*  [{admin_box_support_header}](smarty_tags/admin_box_support_header) - 

*  [{admin_box_support_footer}](smarty_tags/admin_box_support_footer) - 

*  [{admin_box_header}](smarty_tags/admin_box_header) - 

*  [{admin_box_footer}](smarty_tags/admin_box_footer) - 

## Extension TAGs

The following TAGs are available through [Extensions](Extensions), which are linked on their description page.


*  [{tip_of_the_day}](smarty_tags/tip_of_the_day) - assign or display a random tip

*  [{google_analytics}](smarty_tags/google_analytics) - show Google Analytics Javascript code

### News Extension


*  [{news}](smarty_tags/news) - load a list of (categorized) News entries

*  [{news_item}](smarty_tags/news_item) - load one special News Item

*  [{news_category}](smarty_tags/news_category) - fetch all Categories for one News

*  [{news_categories}](smarty_tags/news_categories) - fetch all News Categories

### Comments Extension


*  [{comment_counter}](smarty_tags/comment_counter) - counts the number of comments for an item

*  [{comment_spam_counter}](smarty_tags/comment_spam_counter) - returns the number of "eaten" spam

*  [{comments_latest}](smarty_tags/comments_latest) - fetch (latest) comments

*  [{comments}](smarty_tags/comments) - displays the Comment formular

*  [{gravatar}](smarty_tags/gravatar) - constructs the URL for a gravatar image ([officially named at Gravatar.com](http://en.gravatar.com/site/implement/smarty))

### FAQ Extension


*  [{faq_entries}](smarty_tags/faq_entries) - fetch all entries for one section

*  [{faq_latest}](smarty_tags/faq_latest) - fetch the latest enrties throughout all sections

*  [{faq_section}](smarty_tags/faq_section) - fetch one section by its id

*  [{faq_sections}](smarty_tags/faq_sections) - returns an array of all available sections

### Smileys Extension


*  [{smileys}](smarty_tags/smileys) - a modifier to parse smileys to icons in any string

## Smarty Modifier


*  [{filesize}](smarty_modifier/filesize) - display a formatted filesize (from a bytes value)

*  [{htmlspecialchars}](smarty_modifier/htmlspecialchars) - calls htmlspecialchars on the value

*  [{text_input}](smarty_modifier/text_input) - change " (double quote) ' (single quote) to html entities and call stripslashes

*  [bigace:smarty_modifier:{explode}](smarty_modifier/{explode}) - splits one var into x vars after every defined delimiter

## Smarty Help

Read more about using Smarty int the official Docu at:


*  [Smarty Handbuch - German](http://www.smarty.net/manual/de/)

*  [Smarty Manual - English](http://www.smarty.net/manual/en/)

*  [Extending Smarty with Plugins](http://www.smarty.net/manual/en/plugins.php)


## Writing own Smarty TAGs

Smarty plugin directory: **/addon/smarty/plugins/**


*  Lets assume you want to create the function/TAG {hello_world}

*  Create a file called **/addon/smarty/plugins/function.hello_world.php**

*  Place a function inside:

	:::php
	function smarty_function_hello_world($params, &$smarty) {
	  echo "Hello World, says " . $params['name'] . "!";
	}


*  Call {hello_world name="Bob"} inside your template

The output would be: `Hello World, says Bob!`{html}
