# delete-item

The following cal is made from within the ItemAdminService:

	:::php
	Bigace_Hooks::do_action('delete-item', $itemtype, $id, $language);


If a language version is deleted, the last parameter is set to a locale, otherwise (if the complete item is deleted) the last parameter is null.

## Example usage

	:::php
	Bigace_Hooks::add_action('delete-item', 'deleteItem', 10, 3);
	
	function deleteItem($itemtype, $id, $language = null)
	{
	    $admin = new Bigace_X_Admin($itemtype);
	    if($language !== null) {
	        $admin->deleteLanguage($id, $language);
	    } else {
	        $admin->delete($id);
	    }
	}

