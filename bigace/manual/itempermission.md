# Item permission

In Bigace each object (pages, images, documents) can have one permissions for each existing [Usergroup](groupadmin).  

A permission can have 4 different values for the states:

*  no access (0)

*  read (1)

*  write (3)

*  delete (7)

Each state includes the previous ones, so write includes read.

**Note:**

If a user is member of multiple usergroups, the highest permission is always choosen. For example User A is in group ''Editor'' and ''Admin''. The group ''Editor'' has read permissions and ''Admin'' has write permissions. As group ''Admin'' has more permissions, User A gets ''Admin'' (write) permissions.

## Default permissions

A new item gets by default the permissions from its parent. This can either be a page (when you choose a parent-page during upload) or the TOP-Level Item (which has the ID -1) of the [Itemtype](Itemtype) you add.

As of 2.7.5 there is an Admin GUI to change the default permissions. You can access this page ONLY if you have at least one uploaded image/file, otherwise the link will not be displayed. You find the link to it in the file and image administration panel in the upper right hand corner:
{{:bigace:administration:default-permissions.jpg?600}}

Before 2.7.5 the following applied: \\
The default item permissions for Images and Files (see [Itemtype](Itemtype)) can currently not be changed through the administration. But you can change them using [SQL](database) directly.  


## Setting permissions via SQL

This method is deprecated and should not be used, as there is a new admin GUI to set the permissions (see above).

The table ''group_right'' stores the usergroup-permission mappings, where each usergroup has a link between Usergroup ID, the [Itemtype](Itemtype) and Item ID. 
So we have to update the entries with the Itemtype ID, the Item ID -1 and the usergroup you want to change permissions for.

For example: \\
Change default permissions for Images (ID 4) and the [Group](groupadmin) Admin (ID 40) to permit read, write and read in [Community](Community) 1:

	:::sql
	UPDATE group_right SET `value` = '7' WHERE itemtype = '4' AND cid = '1' AND itemid = '-1' AND group_id = '40';


The default permissions in a fresh installation can be resetted by executing (careful, updates all Communities):

	:::sql
	UPDATE group_right SET `value` = '1' WHERE itemtype = '4' AND itemid = '-1' AND group_id = '0';
	UPDATE group_right SET `value` = '3' WHERE itemtype = '4' AND itemid = '-1' AND group_id = '20';
	UPDATE group_right SET `value` = '3' WHERE itemtype = '4' AND itemid = '-1' AND group_id = '35';
	UPDATE group_right SET `value` = '7' WHERE itemtype = '4' AND itemid = '-1' AND group_id = '40';
	
	UPDATE group_right SET `value` = '1' WHERE itemtype = '5' AND itemid = '-1' AND group_id = '0';
	UPDATE group_right SET `value` = '3' WHERE itemtype = '5' AND itemid = '-1' AND group_id = '20';
	UPDATE group_right SET `value` = '3' WHERE itemtype = '5' AND itemid = '-1' AND group_id = '35';
	UPDATE group_right SET `value` = '7' WHERE itemtype = '5' AND itemid = '-1' AND group_id = '40';


Remember to add the [database prefix](manual/database) to the table.
