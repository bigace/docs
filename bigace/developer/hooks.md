# Hooks

Hooks are extension points in the Bigace API, which can be used by [bigace:plugins](plugins) to change or extend default behaviour.

We distinguish between filter and actions. Filter will be applied to an object (mostly some kind of string or array) and return a result. Actions instead will be called/executed and do not return a result.

Bigace uses a slightly customized version of the [Hooks and Filter API from Wordpress](http://codex.wordpress.org/Plugin_API), so reading their documentation will help you to understand how Bigace works.

And here comes a list of all Filter and Actions ...

## Filter


*  **apply_filters('[admin_menu](developer/filter/admin_menu)', $menu)** - The Admin Menu structure is given in $menu, so you can customize the menu to your needs (most often you will add items).

*  **apply_filters('[admin_portlets](developer/filter/admin_portlets)', $portlets, $controllerName, $adminPortlet)** -  If you want to add a portlet to a portlet enabled admin screen, use this filter. The first argument is an array with all portlets instances, the second one is the name of the admin menu displaying the portlets and the last one the controller itself.

*  **apply_filters('[create_item_meta](developer/filter/create_item_meta)', array(), $itemtype)** - Send from the "Create Page" dialog (currently $itemtype is always _BIGACE_ITEM_MENU, but this can change). See [edit_item_meta](developer/filter/edit_item_meta) for more infos.

*  **apply_filters('[credits](developer/filter/credits)', $allCredits)** - If you want to add an entry to the credits screen, use this filter.

*  **apply_filters('[edit_item_meta](developer/filter/edit_item_meta)', array(), $item)** - Called before the Item Attribute screen is rendered (currently only for pages). If you want to add further input fields from your plugin, add an key/value pair entry to the first argument array. Each pair is one collapsable admin box, with "key" = box title and "value" = box content.

*  **apply_filters('[metatags](developer/filter/metatags)', $values, $item)** - Send from the [bigace:developer:viewhelper:metatags](developer/viewhelper/metatags) [bigace:developer:viewhelper](developer/viewhelper) and the [bigace:smarty_tags:metatags](smarty_tags/metatags) [bigace:smarty_tags](smarty_tags), default tags like description, author, robots. Strictly for `<meta>` TAGs. Only operate with the given array.

*  **apply_filters('[metatags_more](developer/filter/metatags_more)', array(), $item)** - Send from the [bigace:developer:viewhelper:metatags](developer/viewhelper/metatags) [bigace:developer:viewhelper](developer/viewhelper) and the [bigace:smarty_tags:metatags](smarty_tags/metatags) [bigace:smarty_tags](smarty_tags), for any additional HTML TAG in the pages `<header>`. Add any HTML string to the array you want.

*  **apply_filters('[dialog_setting_images](developer/filter/dialog_setting_images)', $vars, $id, $language)** - Returns an array with the values for the image inserting/linking dialog.

*  **apply_filters('[dialog_setting_links](developer/filter/dialog_setting_links)', $vars, $id, $language)** - Returns an array with the values for the cms link/url inserting dialog.

*  **apply_filters('[get_pagetypes](developer/filter/get_pagetypes)', $pagetypes)** - An array of lowercased names for all available pagetypes. Pagetype names are controller names in the sense of the Zend Framework. The 'redirect' pagetypes for example points to the Bigace_RedirectController.

*  **apply_filters('[parse_content](developer/filter/parse_content)', $content, $MENU)** - change or inspect parts of the rendered page dynamically

*  **apply_filters('[search](developer/filter/search)', $results, $query, $community, $user)** - Returns an array of SearchResult objects. $results is an array of already found SearchResult objects. $query is the Zend_Search_Lucene_Search_Query phrase and $community is the Community we are searching for. $user is either null or a Bigace_Principal object. In case $user is a object, the search should respect the users permissions.

*  **apply_filters('[unique_name](developer/filter/unique_name)', $name)** - prepares the unique name for an item (you could replace language specific values with ascii characters)
## Actions


*  **do_action('[delete-item](developer/action/delete-item)', $itemtype, $id, $language = null)** - deletes either an item completely or (if third parameter is not null) a language version 

*  **do_action('[smarty_tpl_header](developer/action/smarty_tpl_header)', $MENU)** - a template hook that should be executed in the `<head>` section of your template

*  **do_action('[smarty_tpl_footer](developer/action/smarty_tpl_footer)', $MENU)** - a template hook that should be executed in the "content" section of your template (at the end of the content, right before the footer starts)

*  **do_action('[page_header](developer/action/page_header)', $MENU)** - Send from the Smarty and Menu command, right before the pages layout is rendered. Register to send additional header() for example.

*  **do_action('[update_item](developer/action/update_item)', $itemtype, $id, $langid, $values, $timestamp)** - Called when updating an Item (its not guaranteed that this happens before or after the item was saved). $values is the array with all submitted item properties. If you use project fields, fetch the required values from $_POST.

*  **do_action('tpl_header', $MENU)** - inside the html head of your template

*  **do_action('tpl_footer', $MENU)** - in a templates footer

*  **do_action('uninstall_community', Bigace_Community $community)** - Send when a community is uninstalled.

*  **do_action('create_item', $this->getItemtypeID(), $id, $langid)** - Called when an Item was created.

*  **do_action('[admin_header](developer/action/admin_header)')** - FIXME

*  **do_action('[admin_footer](developer/action/admin_footer)')** - FIXME

*  **do_action('[application_header](developer/action/application_header)', $MENU)** - FIXME

*  **do_action('[admin_html_head](developer/action/admin_html_head)')** - FIXME

*  **do_action('[init_view](developer/action/init_view)', $view)** - FIXME

*  **do_action('[flush_cache](developer/action/flush_cache)')** - FIXME

*  **do_action('[expire_page_cache](developer/action/expire_page_cache)')** - FIXME

*  **do_action('[save_content](developer/action/save_content)', $item, $content)**

*  **do_action('[delete_content](developer/action/save_content)', $item, $content = null)**

## See also

*  [Hooks API](http://dev.bigace.org/api/latest/Bigace/Bigace_Hooks.html)

*  [Wordpress Plugin API](http://codex.wordpress.org/Plugin_API)

*  [Wordpress Filter API](http://codex.wordpress.org/Plugin_API#Filters)
