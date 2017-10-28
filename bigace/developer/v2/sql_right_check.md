# Item right check in SQL Queries

Most of the right checks that has to be performed are kept in the lowest level, the SQL scripts. This brings a enormous performance boost, cause there are only a few checks to be performed within the PHP Code.

**There are right checks in the following SQL Files:**

    * item_tree_walker.sql (SimpleItemTreeWalker)
    * search_item_fulltext.sql (ItemSearch)
    * item_select_last_edited.sql (ItemService)
    * item_is_leaf.sql (ItemService)
    * item_count_all.sql (ItemService::countAllItems())

For each of these files, there is a file without the right checks (which will only be used for the SuperUser) called {filename}_no_rights.sql.

Here {filename} must be replaced by the original Filename without extension, for example:

item_count_all.sql => item_count_all_no_rights.sql
