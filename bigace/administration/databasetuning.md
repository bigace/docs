# Database Tuning

You have the abbility to define which columns may be fetched from the Database for Item calls. 

A configuration holds all columns for the several Itemtypes. 

Look at the File [/consumer/cid{CID}/config/config.select.inc.php](bigace/cid_cid) for further information. Tuning these select columns may result in better performance.

**Tip:** If the system might not be running after modifing the configuration, use the backup file from **/consumer/cid{CID}/config/config.select.inc.php**.
