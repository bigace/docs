# Database Framework

BIGACE comes with a database abstraction layer, that can be switched using the [Services Framework](developer/services).

You can access it, using the global object:

	:::php
	$GLOBALS['_BIGACE']['SQL_HELPER']


**Please note:** Fetching CMS specific data should always be done by using the the proper [PHP API](php_api) methods.

## Load a Statement

Load a Statement from the folder **/system/sql/** by passing its name (for example **foo.sql**) without the extension:

	:::php
	$sql = $GLOBALS['_BIGACE']['SQL_HELPER']->loadStatement('foo');



## Prepare Statements

If you use replacer in your Statement, you have to prepare the Statement for execution.

	:::php
	$sql = "SELECT * FROM {DB_PREFIX}user WHERE cid={CID} AND id={USER_ID} AND name={NAME}";
	$values = array('USER_ID' => '123', 'NAME' => 'admin');
	
	$sql = $GLOBALS['_BIGACE']['SQL_HELPER']->prepareStatement($sql, $values, true);


The last call gives you the ready to execute SQL Statement:

	:::php
	$result = $GLOBALS['_BIGACE']['SQL_HELPER']->execute($sql);


You see the two replacer **{DB_PREFIX}** and **{CID}**? We did not pass values for those. But why?!?

The answer is easy, these are auto-global values, that will be fetched from the system environment and automatically replaced.

## Escaping

The third parameter (a boolean) in the prepareStatement() call indicates, wheter the values will be escaped or not. 

You might skip this parameter (default is false), when escaping would cause trouble.

For security reason, it is recommended to use "true", that way the DB Framework handles the escaping.

## Executing Statements

Execute a Stement by calling: 

	:::php
	$result = $GLOBALS['_BIGACE']['SQL_HELPER']->execute($sql);
	$id = $GLOBALS['_BIGACE']['SQL_HELPER']->insert($sql); // for auto_increment values


## Reading results

Count results:

	:::php
	$amount = $result->count();


Fetch first result:

	:::php
	$first = $result->next();


Loop through results:

	:::php
	$amount = $result->count();
	for($i=0; $i < $amount; $i++) {
	  $current = $result->next();
	}


