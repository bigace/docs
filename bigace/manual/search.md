# Search

The search used by BIGACE is based on the [MySQL Full-Text Search](http://dev.mysql.com/doc/refman/4.1/en/fulltext-search.html).

If you have problems finding the Menus or Files you are searching for, there might be a couple or reasons:

    * Your search term is too short (following is taken from the MySQL Docu):
      “The default minimum length of words that are found by full-text searches is four characters.”

    * There are not enough entrys in the Database (you need at least three items in the searched Itemtype):
      “The 50% threshold has a significant implication when you first try full-text searching to see how it works: If you create a table and insert only one or two rows of text into it, every word in the text occurs in at least 50% of the rows. As a result, no search returns any results. Be sure to insert at least three rows, and preferably many more...”

    * There might be an encoding Problem between PHP/Webserver/Database.

# Search restriction

There are a lot of words and abbreviations with at least three character, that make totaly sense to be searched: hot, hat, pie, Tim, LOL ...

If you want to search for words less than 4 character, you have to change your MySQL server settings. 
This option normally only applies to user running their own (dedicated/virtual) server.

Edit your /etc/mysql/my.cnf (well, your config file might be named and stored differently) and add these two lines:

	:::ini
	[mysqld]
	ft_min_word_len=3
	
	[myisamchk]
	ft_min_word_len=3


The perform index rebuilds:

	:::sql
	REPAIR TABLE cms_item_1 QUICK ;
	REPAIR TABLE cms_item_4 QUICK ;
	REPAIR TABLE cms_item_5 QUICK ;


Please read this documentation carefully:
[http://dev.mysql.com/doc/refman/5.0/en/fulltext-fine-tuning.html](http://dev.mysql.com/doc/refman/5.0/en/fulltext-fine-tuning.html)

You still might need to patch some BIGACE files, if you are running an version < 2.5.
Please contact us in the Forum in that case.
