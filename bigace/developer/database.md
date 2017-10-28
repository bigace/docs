# Database

This page gives you a quick insight into the Bigace database environment.


## Prefix

During installatiopn you have choosen a database prefix (default is "cms_") which must be appended to every table name / SQL.

Whenever you see a Database query in the manual, you need to change the table name and prepend that prefix value.

For example, if your prefix is "cms_", the query:

	:::sql
	SELECT * FROM item_1 WHERE cid = '1' and language = 'en';

would be rewritten to:

	:::sql
	SELECT * FROM cms_item_1 WHERE cid = '1' and language = 'en';



## Tables

These are default tables in a Bigace installation (v3). Older versions may be different (see "other tables" below).

 | NAME               | DESCRIPTION                                                                                                                                                                                          | 
 | ----               | -----------                                                                                                                                                                                          | 
 | autojobs           | -                                                                                                                                                                                                    | 
 | category           | -                                                                                                                                                                                                    | 
 | configuration      | -                                                                                                                                                                                                    | 
 | content            | -                                                                                                                                                                                                    | 
 | frights            | -                                                                                                                                                                                                    | 
 | future_user_right  | -                                                                                                                                                                                                    | 
 | generic_entries    | -                                                                                                                                                                                                    | 
 | generic_mappings   | -                                                                                                                                                                                                    | 
 | generic_sections   | -                                                                                                                                                                                                    | 
 | groups             | -                                                                                                                                                                                                    | 
 | group_frights      | -                                                                                                                                                                                                    | 
 | group_right        | -                                                                                                                                                                                                    | 
 | id_gen             | -                                                                                                                                                                                                    | 
 | item_1             | All pages in the system.                                                                                                                                                                             | 
 | item_4             | All images in the system.                                                                                                                                                                            | 
 | item_5             | All files in the system.                                                                                                                                                                             | 
 | item_category      | -                                                                                                                                                                                                    | 
 | item_future        | -                                                                                                                                                                                                    | 
 | item_history       | -                                                                                                                                                                                                    | 
 | item_project_num   | -                                                                                                                                                                                                    | 
 | item_project_text  | -                                                                                                                                                                                                    | 
 | logging            | Holds log entries if Database logging is enabled (which is the default setting). You can truncate/empty this table, but note that you loose all log information. You can skip this table in backups. | 
 | plugins            | -                                                                                                                                                                                                    | 
 | session            | Currently active user session.                                                                                                                                                                       | 
 | unique_name        | -                                                                                                                                                                                                    | 
 | user               | -                                                                                                                                                                                                    | 
 | user_attributes    | Metadata for all user. Each row is one meta-attgribute for a user, who can have unlimited entries.                                                                                                   | 
 | user_group_mapping | Mapping table between User and Groups.                                                                                                                                                               | 

## Other tables

These tables can come from a plugin or a different Bigace version.

 | NAME               | ORIGIN                         | DESCRIPTION                                                                                                                                                                                 | 
 | ----               | ------                         | -----------                                                                                                                                                                                 | 
 | statistics         | Bigace 2.7 / Statistics Plugin | Holds statistical information about visitors, if Statistics are enabled. You can truncate/empty this table, but you will loose all hisotric statistics. You can skip this table in backups. | 
 | statistics_history | Bigace 2.7 / Statistics Plugin | Unused, as the planned feature were never implemented. This tables could even be deleted.                                                                                                   | 

