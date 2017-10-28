# Creating Admin Theme in v2.x

When you are going to create a new Admin Style you have to follow only some easy rules.

Each Admin Style has its own Directory below **/public/system/style/**. When first creating your Style, copy everything from the "standard" Theme and replace the files (with same names) with your ones.


*  [General information about Admin Themes](bigace/admin_themes)

*  [A list of all available Admin Themes](bigace/extensions/admintheme)


## Directory Structure

Create the following directory Structure:

	
	--- StyleName
	   |
	   +--- style.css
	   |
	   |-------- editor
	   | 
	   +-------- error
	   |
	   +-------- menutree
	   |
	   +-------- languages
	   |
	   +-------- templates




## Required files

These are the Files of the main Folder:

    * style.css
    * active.png
    * category_link.png
    * category_new.png
    * category_unlink.png
    * delete.png
    * down.png
    * edit.png (added for 2.5)
    * empty.gif
    * failure.png
    * history.png
    * inactive.png
    * info.png
    * manual.png
    * portlets.png
    * success.png
    * up.png
    * update_perform.png
    * user.png
    * userdata.png
    * user_active.png
    * user_add.png
    * user_delete.png
    * user_group.png
    * user_inactive.png
    * refresh.png
    * user_edit.png
    * password.png
    * download.png
    * menu_fckeditor.png
    * menu_htmleditor.png
    * item_1.png
    * item_4.png
    * item_5.png
    * item_1_back.png
    * item_1_new.png
    * item_4_new.png
    * item_5_new.png
    * access_denied.png
    * user_group_admin.png
    * user_group_delete.png
    * user_group_add.png
    * category_go.png
    * history_recover.png
    * history_delete.png
    * save.png
    * cut.png
    * copy.png
    * paste.png
    * reorder.png
    * folder_in.png
    * folder_out.png
    * arrow_ltr.png
    * back.png
    * rights.png
    * up_top.png
    * down_bottom.png

## Deprecated Files

    * `<del>`category_edit.png`</del>` (removed with 2.5)
    * `<del>`new.gif`</del>` (removed with 2.0)
    * `<del>`new_menu.gif`</del>` (removed with 2.0)
    * `<del>`preview.gif`</del>` (removed with 2.0)
    * `<del>`arrow_ltr.gif`</del>` (removed with 2.0)
    * `<del>`back.gif`</del>` (removed with 2.0)
    * `<del>`rights.gif`</del>` (removed with 2.0)
    * `<del>`edit.gif`</del>` (removed with 2.0)
    * `<del>`standard.php`</del>` (removed with 2.0)
    * `<del>`up_dir.png`</del>` (removed with 2.0)
    * `<del>`open_dir.png`</del>` (removed with 2.0)
    * `<del>`empty.gif`</del>` (removed with 2.0)

