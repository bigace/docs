# UTF-8 conversion helper

This script will help you with the UTF-8 conversion.
Please remember to create a **database backup** before execution! If anything fails, you need that database dump to revert the changes.

## Step-by-Step

 1.  Find out which collation your database currently uses (see below)
 2.  Create the file **utf8.php** in your BIGACE root folder
 3.  Copy the code from below into the **utf8.php** script
 4.  Open it in your browser
 5.  Select your collation (from step 1) from the select box and hit "Convert"
 6.  You should see "**Congratulations, your data was converted!**"
 7.  If you see errors, please report them in the [Forum](http://forum.bigace.de/)
 8.  Delete the file "utf8.php"


## Detect current collation

Its simple to find your database collation using phpMyAdmin. 

See this screenshot:

{{bigace:administration:utf8-2.jpg}}

This installation used **latin1_swedish_ci** as collation.

Another one of my installations runs with **latin1_german2_ci**, as you can see here:

{{bigace:administration:utf8-3.jpg}}

You could also execute the following SQL statement:

	:::sql
	SELECT collation( 'your-database-name' ) 

Note: The result must NOT be the collation of all your tables. If possible use phpMyAdmin to find the tables collation.

This value is what you must select in the drop down at Step 5.


## Conversion helper code

Please note, the conversion helper is meant to be helpful, it worked for me and others as well, BUT: 

**I do not guarantee that it will work in every environment. The code is provided as is and without any warranty.** 

	:::php
	<?php
	
	require_once(dirname(__FILE__) . '/system/config/config.system.php');
	
	mysql_connect($_BIGACE['db']['host'], $_BIGACE['db']['user'], $_BIGACE['db']['pass']);
	mysql_select_db($_BIGACE['db']['table']);
	 
	if(!isset($_POST['convert_from'])) 
	{
		print "<h1>DID YOU CREATE A BACKUP ?!? If not, do it first!</h1>";
		print '<form action="'.$_SERVER['PHP_SELF'].'" method="post">';
		print "Select your database collation: ";
		print '<select name="convert_from">';
	
		$charsets = mysql_query(" SHOW COLLATION ") or die(mysql_error());
		while ($char_row = mysql_fetch_row($charsets)) {
			print '<option value="'.$char_row[0].'"';
			if($char_row[0] == 'latin1_german1_ci')
				print " selected";
			print '>'.$char_row[0].'</option>';
		}
	
		print '</select>';
		print '<input type="submit" value="Convert">';
		print '</form>';
	}
	else
	{
		$convert_from = $_POST['convert_from'];
	
		set_time_limit(0); 
	
		// collation you want to change it to:
		$convert_to   = 'utf8_general_ci';
		 
		// character set of new collation:
		$character_set= 'utf8';
		 	 
		$rs_tables = mysql_query(" SHOW TABLES ") or die(mysql_error());
		$error_occured = false;
		print '<pre>';
		while ($row_tables = mysql_fetch_row($rs_tables)) {
			// only convert prefixed tables OR all if an empty prefix was used
			if(strlen($_BIGACE['db']['prefix']) == 0 || stripos($row_tables[0], $_BIGACE['db']['prefix']) !== false)  
			{
				$table = mysql_real_escape_string($row_tables[0]);
			
				$conv_table_sql = "ALTER TABLE `$table` DEFAULT CHARACTER SET $character_set;";
				mysql_query($conv_table_sql);
				if(mysql_errno() != 0) {
					echo $conv_table_sql . "\r\n";
					echo "<b>".mysql_error()."</b>\r\n";
					$error_occured = true;
				}
		
				$conv_started = false;
				$conv_sql = "ALTER TABLE `$table`";
				$rs = mysql_query(" SHOW FULL FIELDS FROM `$table` ") or die(mysql_error());
				while ($row=mysql_fetch_assoc($rs)) {
					
					if ($row['Collation']!=$convert_from) {
					    continue;
					}
	
					// Alter field collation:
					$field = mysql_real_escape_string($row['Field']);
					if($conv_started)
						$conv_sql .= ", ";
					$conv_sql .= " CHANGE `$field` `$field` $row[Type] CHARACTER SET $character_set COLLATE $convert_to";
					$conv_started = true;
				}
				$conv_sql .= ";";
	
				// execute the conversion if at least one column with old collation was found
				if($conv_started) {
					mysql_query($conv_sql);
					if(mysql_errno() != 0) {
						echo $conv_sql." \r\n";
						echo "<b>".mysql_error()."</b>\r\n";
						$error_occured = true;
					}
				}
			}
		}
		print "</pre>";
	
		if($error_occured)
			echo '<h1>An error occured :( <a href="http://forum.bigace.de">Please contact us at the Forum</a>.</h1>';
		else
			echo '<h1>Congratulations, your data was converted!</h1>';
	}
	?>

This code was inspired by [http://www.phpwact.org/php/i18n/utf-8/mysql](http://www.phpwact.org/php/i18n/utf-8/mysql). Thanks!


If you want to convert your database at the end, you can use the following statement (where "DatabaseName" must be the name of your BIGACE database).

	:::sql
	ALTER DATABASE `DatabaseName` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci 

