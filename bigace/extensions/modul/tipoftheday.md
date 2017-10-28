# Tip of the Day

Tip of the Day is a [Extension](bigace/extensions) Module, which displays a random "tip", consisting of a "title", "link" and "text".
Tips are stored in your BIGACE DB in a separate table.
 
Tips can be added, modified or deleted with a new Administration Panel, see "Extensions" -> "Tip of the Day".

With each request, one random "tip" is fetched from the pool.

`<WRAP center round download>`

Get all downloads from:

[Tip-of-the-Day detail page](http://www.bigace.de/plugins/detail/11-Tip+of+the+Day)

`</WRAP>`

## Permissions

To edit the tips, you must be the [SuperUser](bigace/manual/superuser) OR you 
assign the [GroupPermission](bigace/manual/grouppermission) "tipoftheday" and 
assign it to your administrating [UserGroup](bigace/manual/groupAdmin).

## Integration by Module

If you want to use the module "Tip of the day" add the following Code to your page content:


*  {TIP-OF-THE-DAY} = the text of the tip

*  {NAME-OF-THE-DAY} = the title of the tip

*  {LINK-OF-THE-DAY} = the url of the tip

The replacement will be done ONLY if {TIP-OF-THE-DAY} can be found within the menus content.
Otherwise the Tip will be appended at the Pages Bottom. 

## Integration by Smarty TAG

Have a look at the [{tip_of_the_day}](bigace/smarty_tags/tip_of_the_day) Smarty TAG docu.


