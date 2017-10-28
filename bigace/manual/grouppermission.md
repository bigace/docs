# Group Permissions

Group permissions where called **functional rights** in the last versions.

Group Permissions most often protect admin panel and application access. They are linked to  [User Groups](bigace/manual/groupadmin).

If a User is member of several [User Groups](bigace/manual/groupadmin), the highest (positive) permissions will be used.

## Permission listing

The following listing is an overview of all existing group permission.


*  admin_categorys - Allows to administrate Categories (edit, create, move and delete Categories).

*  admin_configurations - Allows to change Configurations.

*  admin_items - Allows to administrate Items (edit, upload ad delete Images and Files).

*  admin_menus - Allows to administrate Menus (create and delete Menus).

*  admin_users - Allows to administrate User (edit, create and delete user, change Group mapping).

*  autojobs.admin - Configure and activate/deactivate autojobs.

*  community.admin - Allows to edit the Community-Domain Mapping for all Communities.

*  community.deinstallation - Allows to deinstall Communities. **SECURITY WARNING!**

*  community.installation - Allows to add new Communities to this installation.

*  community.maintenance - Allows to edit the Website Maintenance State and Message.

*  edit.portlet.settings - Allows to open, edit and save the Portlet settings for each Page, the User has write rights on.

*  edit.usergroup - Allows to edit the Usergroups and their Member links.

*  editor.html.sourcecode - Allows to access the HTML Sourcecode.

*  edit_frights - Allows to administrate the User Group Permission.

*  edit_items - Allows to edit Items (update existing ones).

*  edit_menus - Allows to edit Menus (use Editor, Workflow).

*  edit_own_profile - Allows to edit the Users own Profile.

*  export_database - Allows to export the community database.

*  group_frights - Allows to edit the Group-to-Permission mapping. **SECURITY WARNING!**

*  languages_all_rights - Allows to administrate the languages.

*  logging.messages - Allows to read and clean up all Log messages.

*  module_all_rights - Allows to administrate the installed modules.

*  smarty.designs.edit - Edit existing and create new Page Designs.

*  smarty.stylesheets.edit - Edit existing and create new Stylesheets.

*  smarty.templates.edit - Edit existing and create new Smarty Templates.

*  system_admin - Allows access to some hidden admin plugins.

*  updates_manager - Allows to manage and install Updates.

*  use_editor - Allows to edit page content with an editor. If deactivated the [{permission_editcontent}](bigace/smarty_tags/permission_editcontent) TAG will return false.

*  view_statistics - Allows to view statistics.

## Example

**User:**

    * User A is member of the Usergroups B1 and B2
    * User B is member of the Usergroups B1
    * User C is member of the Usergroups B2 and B3

**Usergroups:**

    * Group B1 has the Group permissions F1 und F2
    * Group B2 has the Group permissions F1 und F4
    * Group B3 has the Group permissions F3 and F4

**Results:**

    * User A has therefor the permissions F1, F2 and F4
    * User B has therefor the permissions F1 and F2
    * User C has therefor the permissions F1, F3 and F4

