# Reset a users password with SQL

This article describes quickly how you can find a user in the database and how you can reset a password with plain SQL.

You need to find out your [Community ID](bigace/manual/community) first, which you can see in the administration, the Community config file or in the hidden page footer. Please insert this CID in the next SQL queries where you see {CID}. 

Please also extend the tablename "user" with the [database prefix](bigace/manual/database) if you use one.

## Find (a) user in the database

Find all in the Community:

	:::sql
	SELECT * from user WHERE cid = {CID};


Find one user by its email:

	:::sql
	SELECT * from user WHERE cid = {CID} AND email = '{EMAIL}';

*Replace {EMAIL} with the real email-adress.*

## Reset a users password

The SQL to change one user in the database is the following:

	:::sql
	UPDATE user SET password = md5('{PASSWORD}') WHERE cid = {CID} and id = {ID};

*Replace {PASSWORD} with the new password and {ID} with the ID you just found out with one of the "search queries" above.*

